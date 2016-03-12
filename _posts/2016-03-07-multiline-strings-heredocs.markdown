---
layout: post
title:  "Multiline Strings / Heredocs"
date:   2016-03-07 08:15:58 -0600
categories: string
---
This example shows how to create a multiline string.

# First line break is removed
{% highlight elixir %}
"  1\n  2\n  3\n" = """
  1
  2
  3
"""

# Whitespace before trailing `"""` will remove
# whitespace up to the same indentation
# on each line
  "1\n2\n3\n" = """
                1
                2
                3
                """  

# Heredoc sigils can also be used
# Interpolated
"""
\"#{1}\"
\"#{2}\"
"""
# Not Interpolated
"""
"1"
"2"
"""

{% endhighlight %}
