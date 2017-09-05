---
layout: post
title:  "Reescribir url con Nginx!"
date:   2017-08-22 10:13:09 -0300
categories: code
---

Si necesitas rescribir la url de un sitio web de manera rapida y simple como github.io (aplicado en este blog), una App de Heroku por ejemplo de algo como https://nombre.dominioexterno.com a https://mi.dominio.com.

En Nginx tienes la siguiente configuración, muy simple. En mi caso para el dominio https://eliasleyton.com desde https://eliasleyton.github.io.

{% highlight Nginx config files %}
location  / {
  rewrite /(.*) /$1  break;
  proxy_pass https://eliasleyton.github.io;
}
{% endhighlight %}

Si quieren siquisieran usar por ejemplo https://midominio.com/blob seria.

{% highlight Nginx config files %}
location  /blog {
  rewrite /(.*) /$1  break;
  proxy_pass https://eliasleyton.github.io;
}
{% endhighlight %}
