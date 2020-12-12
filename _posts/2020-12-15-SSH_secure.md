---
layout: post
title: "Linux - SSH 관련 보안설정"
description: "Linux - SSH 관련 보안설정"
categories: [linux]
tags: [jekyll, linux, ssh, 보안설정, ssh-key]
redirect_from:
  - /2020/12/15/
---

> This is code blocks and highlighting test page for [Simple Texture][Simple Texture] theme.

* Kramdown table of contents
{:toc .toc}

# Root 접속 제한

많은 사이트에서 보안상의 이유로 SSH 접속을 할때 root로 바로 접근되는것을 막아 놓습니다.

ssh 사용시 가장 기본이 되는 보안설정으로 어떻게 하는지 한번 알아보겠습니다.

## user 생성

말 그대로 root 직접 접근을 막게 될 경우 접속 및 실제 사용자가 사용할 user를 생성해 줍니다.
여기서는 bbang01 로 생성하겠습니다.

~~~~~~~~~~~~~~~~~~~~~~
# useradd -m bbang01
~~~~~~~~~~~~~~~~~~~~~~

useradd 명령어를 사용할때는 아래 처럼 간단하게 옵션을 선택해서 적용할수있습니다.

> -m : user생성시 home 디렉터리도 함께 생성 ( ex: /home/bbang01 )
>
> -g : 1차 그룹 지정  /  -G : 2차 그룹 지정
>
> -d : 임의로 home 디렉터리를 지정
>
> -s : 사용자 생성시 사용할 셀을 지정
>
> -u : UID 값을 지정하여 생성

그 뒤에는 생성한 user인 *`bbang01`*의 패스워드를 지정해 줍니다.

~~~~~~~~~~~~~~~~~~~~~~
# passwd bbang01
Changing password for user bbang01.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
~~~~~~~~~~~~~~~~~~~~~~

## root 직접 접근 제한

ssh의 설정은 `/etd/ssh/` 아래에 있는 파일들의 설정으로 이루어 집니다.



This is a test for inline codeblocks like `C:/Ruby23-x64` or `SELECT  "offices".* FROM "offices" `

Here is a literal `` ` `` backtick.
And here is a Ruby code fragment `x = Class.new`{:.language-ruby}

# Fenced Code Blocks

~~~~~~~~~~~~
~~~~~~~
code with tildes
~~~~~~~~
~~~~~~~~~~~~~~~~~~

# Simple codeblock with long lines

    function myFunction() {
        alert("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
    }

# Language of Code Blocks

~~~ ruby
def what?
  42
end
~~~

# Highlighted

## External Gist

<script src="https://gist.github.com/yizeng/9b871ad619e6dcdcc0545cac3101f361.js"></script>

## Simple Highlight

{% highlight ruby %}
def foo
  puts 'foo'
end
{% endhighlight %}

## Highlight with long lines

{% highlight c# %}
public class Hello {
    public static void Main() {
        Console.WriteLine("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
    }
}
{% endhighlight %}

## Highlight with line numbers and long lines

{% highlight javascript linenos=table %}
function myFunction() {
    alert("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
}
{% endhighlight %}

[^1]: This is a footnote.

[kramdown]: https://kramdown.gettalong.org/
[Simple Texture]: https://github.com/yizeng/jekyll-theme-simple-texture
