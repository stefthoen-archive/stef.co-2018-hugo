---
layout: post
title:  "Sprintf"
date:   2017-01-10 22:00:00 +0100
categories: php
---
I've been using the `sprintf()` and `printf()` methods from the PHP standard
library and I recently found out that you can re-use variables by changing the
syntax in the format strings.

Where I use to write:
{{< highlight php >}}
<?php
echo sprintf(
    'The %s contains %d monkeys.
    That\'s a nice %s full of %d monkeys.',
    $location,
    $num,
    $location,
    $num);
{{< /highlight >}}

It's easier to write:
{{< highlight php >}}
<?php
echo sprintf(
    'The %2$s contains %1$d monkeys.
    That\'s a nice %2$s full of %1$d monkeys.',
    $num,
    $location);
{{< /highlight >}}
