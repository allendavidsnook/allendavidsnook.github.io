---
title: Un-Expected Value and a Slow Snake
---

I just finished the latest course towards my Masters in Electrical Engineering at UW &#8211; Probability and Random Processes for Electrical Engineering. And yeah, I got an A (&gt;100%). And I&#8217;m glad I took it even though I had, years and years ago, taken Stochastics at Johns Hopkins. Although core concepts like probabilities, random variables and the like haven&#8217;t changed, the options available to engineers for numerical methods seem more practical now.



Our final project involved using a Naïve Bayes Classifier to classify handwritten digits from the large MNIST database ( http://yann.lecun.com/exdb/mnist/ ). First you train your classifier against 60,000 training images (handwritten digits from 0 to 9) and then you run 10,000 test images against the classifier and see how well it identifies the digits in the images. I don&#8217;t remember doing anything like this in the Stochastics course at Hopkins, and it was fun to translate Bayes&#8217; Theorem into code and even more fun to see it work.



That was the un-expected value in taking the course again (and it freed up transfer options which will allow me to take a Comp Sci IoT course next quarter and have it count towards my MSEE.) (BTW &#8211; that&#8217;s a probability pun there &#8211; un-expected value &#8211; get it?! Wokka wokka.)



I wrote the classifier first in MATLAB (we get a generous student license for this powerful not-free software) and then again in Python with NumPy ( https://numpy.org ) (because all the cool kids are trying ML with Python and although some assembly is required, Python and NumPy are free [including as in beer].)



Both MATLAB and Python/NumPy yielded the same results:







Basically, when presented with a &#8220;0&#8221; digit, the classifier correctly identified it as a &#8220;0&#8221; 90% of the time (or incorrectly as a &#8220;5&#8221; about 5% of the time and so on and so forth.)



What I didn&#8217;t expect was how SLOW Python was to do the same work. MATLAB processed all the data in about 5 seconds but Python took almost 3 minutes to do the same work. The majority of that difference I suspect comes down to MATLAB scripts being compiled into native code before execution whereas Python is interpreted on the fly. Then again, for free software, it does open access to numerical methods for those without access to the professional tool, so that&#8217;s a positive &#8211; it reminds me of some of what we run into with WooCommerce and how I see native code projects like PeachPie ( https://www.peachpie.io ) as a potential game changer for performance.



While researching the speed difference, I came across this article that sums it all up well and in a funny light:



MATLAB is the BMW sedan of the scientific computing world. It’s expensive, and that’s before you start talking about accessories (toolboxes). You’re paying for a rock-solid, smooth performance and service. It also attracts a disproportionate amount of hate.Python is a Ford pickup. It’s ubiquitous and beloved by many (in the USA). It can do everything you want, and it’s built to do some things that other vehicles can’t. Chances are you’re going to want to borrow one now and then. But it doesn’t offer a great pure driving experience.Toby Driscoll, https://tobydriscoll.net/blog/matlab-vs.-julia-vs.-python/ 



I&#8217;m glad when I have access to or can afford &#8220;BMW&#8221; level tools, but I also appreciate the experimenting, low risk prototyping and access that &#8220;Ford&#8221; level tools unlock.
