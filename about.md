---
published: true
permalink: /about.html
layout: hero
filename: about.md
title: آزمایشگاه مدلسازی فرآیند دانا
desc: آزمایشگاه دانا، یک پروژه متن باز جهت توسعه نرم افزار مدلسازی فرآیند، براساس معادلات و با اهداف آموزشی می باشد
---

[![Go to server website](/assets/img/DANA_ServerSmall.png "DANA-Laboratory Client Site")](/DANA-Laboratory.jl)
[![Go to client website](/assets/img/DANA_ClientSmall.png "DANA-Laboratory Server Site")](/DANA-Laboratory.java)

##شرکت ره آوران فنون پتروشیمی

پروژه دانا با حمايت شرکت ره آوران فنون پتروشيمي آغاز شده است.
[شرکت ره آوران فنون پتروشيمي](http://www.rfpc.ir/)، از شرکت هاي زير مجموعه [هلدينگ پتروشيمي خليج فارس](http://www.pgpic.ir) واقع در ماهشهر، سايت 3 منطقه ويژه اقتصادي بندر امام است.
اين شرکت ارائه دهنده خدمات آموزشي به کارکنان و کارآموزان شرکت هاي فعال در صنعت نفت مي باشد.

##دکتر سالم بعنونی
[دکتر سالم بعنونی](http://engg.scu.ac.ir/banooni) استادیار دانشگاه چمران اهواز و از اساتید شرکت ره آوران از مشوقین و مشاورین این پروژه می باشند

##خانه مهندسی جوان اهواز
مجموعه خانه مهندسین جوان اهواز[مجموعه خانه مهندسین جوان اهواز](http://www.ayehco.com/)، و مهندس [خوران](http://engg.scu.ac.ir/khooran)  مدیریت محترم مجموعه از مشاورین و حامیان پروژه دانا می باشند


~~~julia
  function testIDealGasForNonlinearSolver()
    ######Temprature is undef#######
    DNIdel=DANAIdealGasEos()
    DNIdel.P=2000.0
    DNIdel.Cp=629657.0
    DNIdel.CASNO="95-63-6"
    DNIdel.usePolynomialEstimationOfCp=true
    DNIdel.C1,DNIdel.C2,DNIdel.C3,DNIdel.C4,DNIdel.C5 = C0Poly("95-63-6")
    setEquationFlow(DNIdel)
    somthingUpdated=true
    fullDetermined=false
    while (somthingUpdated && !fullDetermined)
      rVls,vars=solve(DNIdel)
      println("************one solution done************")
      somthingUpdated,fullDetermined=update!(DNIdel,rVls,vars)
    end
    dump(DNIdel)
    #a=replace(DNIdel)
    #println(a)
  end
~~~

~~~jl
  function testIDealGasForNonlinearSolver()
    ######Temprature is undef#######
    DNIdel=DANAIdealGasEos()
    DNIdel.P=2000.0
    DNIdel.Cp=629657.0
    DNIdel.CASNO="95-63-6"
    DNIdel.usePolynomialEstimationOfCp=true
    DNIdel.C1,DNIdel.C2,DNIdel.C3,DNIdel.C4,DNIdel.C5 = C0Poly("95-63-6")
    setEquationFlow(DNIdel)
    somthingUpdated=true
    fullDetermined=false
    while (somthingUpdated && !fullDetermined)
      rVls,vars=solve(DNIdel)
      println("************one solution done************")
      somthingUpdated,fullDetermined=update!(DNIdel,rVls,vars)
    end
    dump(DNIdel)
    #a=replace(DNIdel)
    #println(a)
  end
~~~

{% highlight pygments.lexers.math.JuliaLexer %}
  function testIDealGasForNonlinearSolver()
    ######Temprature is undef#######
    DNIdel=DANAIdealGasEos()
    DNIdel.P=2000.0
    DNIdel.Cp=629657.0
    DNIdel.CASNO="95-63-6"
    DNIdel.usePolynomialEstimationOfCp=true
    DNIdel.C1,DNIdel.C2,DNIdel.C3,DNIdel.C4,DNIdel.C5 = C0Poly("95-63-6")
    setEquationFlow(DNIdel)
    somthingUpdated=true
    fullDetermined=false
    while (somthingUpdated && !fullDetermined)
      rVls,vars=solve(DNIdel)
      println("************one solution done************")
      somthingUpdated,fullDetermined=update!(DNIdel,rVls,vars)
    end
    dump(DNIdel)
    #a=replace(DNIdel)
    #println(a)
  end
{% endhighlight %}