---
layout: default
title: Adding Graviatar to you app
permalink: gravatar
---

# 앱에 그라바타트를 넣습니다.

*Created by Catherine Jones*

[앱 개발 가이드](http://guides.railsgirls.com/app/)와 [디바이즈](http://guides.railsgirls.com/devise/) 젬으로 인증하기를 따라서 레일스 걸스 앱스를 이미 만들어두어야 합니다.

### Important

여기서는 그라바타에 이메일 주소를 등록해두어야 합니다. 등록하지 않았다면 [gravatar.com](http://en.gravatar.com/)로 가서 등록할 수 있습니다.

## *1.* Add the Gravtastic gem

gemfile을 수정합니다. `devise` 젬 아래에 다음과 같이 추가합니다.

{% highlight ruby %}
gem 'gravtastic'
{% endhighlight %}

터미널에서 아래와 같이 실행합니다.

{% highlight sh %}
bundle install
{% endhighlight %}

그라바타를 사용하는 젬을 설치하고 레일스 서버를 재시작합니다.

## *2.* Set up Gravatar in your app

`app/models/user.rb` 파일을 수정합니다. 아래와 같이

{% highlight ruby %}
include Gravtastic
gravtastic
{% endhighlight %}

첫째줄 아래에 추가합니다.

## *3.* Configure Gravatar

`app/views/layouts/application.html.erb` 파일을 수정합니다. 

{% highlight erb %}
<% if user_signed_in? %>
{% endhighlight %}

섹션에서 

{% highlight erb %}
<% else %>
{% endhighlight %}

코드 위에 아래와 가이 추가합니다.

{% highlight erb %}
<%= image_tag current_user.gravatar_url %>
{% endhighlight %}

브라우저를 열어서 이메일 주소로 로그인하면 그라바타에 등록한 프로필 사진이 나타납니다.
