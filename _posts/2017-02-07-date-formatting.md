---
date: 2017-02-07
title: Date formatting
video_id: nHCzJsc4KdU
description: Format Jekyll dates
tags:
  - jekyll-liquid
resources:
  - name: Source code
    link: https://github.com/CloudCannon/bakery-store/tree/date-formatting
type: Video
set: intermediate
set_order: 4
---
## Introduction

Formatting dates can be tricky if you need a specific format. In this tutorial we'll show you how to build a date in almost any format.

## Setup

We'll start by setting a date in front matter in [ISO 8601 format](http://www.iso.org/iso/home/standards/iso8601.htm).

{% raw %}
~~~liquid
---
layout: default
title: Date Formatting
date: 2016-03-23T10:20:00Z
---
~~~
{% endraw %}

Now we can run the date through a filter to get the desired format.

## date_to_long_string

Input:
{% raw %}
~~~liquid
{{ page.date | date_to_long_string }}
~~~
{% endraw %}

Output:
~~~html
23 March 2016
~~~

## date_to_rfc822

Input:
{% raw %}
~~~liquid
{{ page.date | date_to_rfc822 }}
~~~
{% endraw %}

Output:
~~~html
Wed, 23 Mar 2016 23:20:00 +1300
~~~

## date_to_string

Input:
{% raw %}
~~~liquid
{{ page.date | date_to_string }}
~~~
{% endraw %}

Output:
~~~html
23 Mar 2016
~~~

## date_to_xmlschema

Input:
{% raw %}
~~~liquid
{{ page.date | date_to_xmlschema }}
~~~
{% endraw %}

Output:
~~~html
2016-03-23T23:20:00+13:00
~~~


## date

`date` gives us complete control of the format. We can specify a template of the format we want. For example.

Input:
{% raw %}
~~~liquid
{{ page.date | date: "%m/%d/%Y" }}
~~~
{% endraw %}

Output:
~~~html
03/23/2016
~~~

or

Input:
{% raw %}
~~~liquid
{{ page.date | date: "%-d %B %Y"}}
~~~
{% endraw %}

Output:
~~~html
23 March 2016
~~~

There's many placeholders we can use for date formatting.
<table>
	<thead>
		<tr>
			<th>Placeholder</th>
			<th>
				Format
			</th>
      <th>
				Example
			</th>
		</tr>
	</thead>
	<tbody>
    <tr>
      <td>%a</td>
      <td>Abbreviated weekday</td>
      <td>Sun</td>
    </tr>
    <tr>
      <td>%A</td>
      <td>Full weekday name</td>
      <td>Sunday</td>
    </tr>
    <tr>
      <td>%b</td>
      <td>Abbreviated month name</td>
      <td>Jan</td>
    </tr>
    <tr>
      <td>%B</td>
      <td>Full month name</td>
      <td>January</td>
    </tr>
    <tr>
      <td>%c</td>
      <td>Preferred local date and time representation</td>
      <td>Fri Jan 29 11:16:09 2016</td>
    </tr>
    <tr>
      <td>%d</td>
      <td>Day of the month, zero-padded</td>
      <td>05</td>
    </tr>
    <tr>
      <td>%-d</td>
      <td>Day of the month</td>
      <td>5</td>
    </tr>
    <tr>
      <td>%D</td>
      <td>Formats the date</td>
      <td>29/01/16</td>
    </tr>
    <tr>
      <td>%e</td>
      <td>Day of the month</td>
      <td>3</td>
    </tr>
    <tr>
      <td>%F</td>
      <td>Returns the date in ISO 8601 format</td>
      <td>2016-01-29</td>
    </tr>
    <tr>
      <td>%H</td>
      <td>Hour of the day, 24-hour clock</td>
      <td>07</td>
    </tr>
    <tr>
      <td>%I</td>
      <td>Hour of the day, 12-hour clock</td>
      <td>04</td>
    </tr>
    <tr>
      <td>%j</td>
      <td>Day of the year</td>
      <td>017</td>
    </tr>
    <tr>
      <td>%k</td>
      <td>Hour of the day, 24-hour clock</td>
      <td>7</td>
    </tr>
    <tr>
      <td>%m</td>
      <td>Month of the year</td>
      <td>04</td>
    </tr>
    <tr>
      <td>%M</td>
      <td>Minute of the hour</td>
      <td>09</td>
    </tr>
    <tr>
      <td>%p</td>
      <td>Meridian indicator uppercase</td>
      <td>AM</td>
    </tr>
    <tr>
      <td>%P</td>
      <td>Meridian indicator lowercase</td>
      <td>pm</td>
    </tr>
    <tr>
      <td>%r</td>
      <td>12-hour time</td>
      <td>01:31:43 PM</td>
    </tr>
    <tr>
      <td>%R</td>
      <td>24-hour time</td>
      <td>18:09</td>
    </tr>
    <tr>
      <td>%T</td>
      <td>24-hour time with seconds</td>
      <td>18:09:13</td>
    </tr>
    <tr>
      <td>%s</td>
      <td>Number of seconds since 1970-01-01 00:00:00 UTC</td>
      <td>1452355261</td>
    </tr>
    <tr>
      <td>%S</td>
      <td>Second of the minute</td>
      <td>05</td>
    </tr>
    <tr>
      <td>%U</td>
      <td>Week number of the current year, starting with the first Sunday as the first day of the first week</td>
      <td>03</td>
    </tr>
    <tr>
      <td>%W</td>
      <td>Week number of the current year, starting with the first Monday as the first day of the first week</td>
      <td>09</td>
    </tr>
    <tr>
      <td>%w</td>
      <td>Day of the week. Sunday is 0</td>
      <td>4</td>
    </tr>
    <tr>
      <td>%x</td>
      <td>Preferred representation for the date</td>
      <td>05/11/15</td>
    </tr>
    <tr>
      <td>%X</td>
      <td>Preferred representation for the time</td>
      <td>17:15:31</td>
    </tr>
    <tr>
      <td>%y</td>
      <td>Year without a century</td>
      <td>16</td>
    </tr>
    <tr>
      <td>%Y</td>
      <td>Year with a century</td>
      <td>2016</td>
    </tr>
    <tr>
      <td>%Z</td>
      <td>Time zone name</td>
      <td>PST</td>
    </tr>
    <tr>
      <td>%%</td>
      <td>Literal % character</td>
      <td>%</td>
    </tr>
  </tbody>
</table>

## Ordinal

One notable exclusion from this list getting the ordinal date. For example we couldn't output "May 23**rd**" because there's no placeholder for the "rd".

A workaround for this is to use Liquid to calculate and output the ordinal.

{% raw %}
~~~liquid
{% assign day = page.date | date: "%-d"  %}
{% case day %}
  {% when '1' or '21' or '31' %}{{ day }}st
  {% when '2' or '22' %}{{ day }}nd
  {% when '3' or '23' %}{{ day }}rd
  {% else %}{{ day }}th
{% endcase %}
{{ page.date | date: "of %B, %Y" }}
~~~
{% endraw %}

~~~html
23rd of March, 2016
~~~
