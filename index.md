<!DOCTYPE html>
<html lang="en">
<head profile="http://www.w3.org/2005/10/profile">
    <meta charset="UTF-8">
    <title>Photography Mapped - Interactive Camera Diagram</title>
    <meta name="description" content="An interactive diagram simulates your camera (Understand your camera &rarr; take better photos)">
    
    <!-- For Open Graph -->
    <meta property="og:title"                        content="Interactive Camera Diagram">
    <meta property="og:description"                  content="An interactive diagram simulates your camera (Understand your camera &rarr; take better photos)">
    <meta property="og:type"                         content="product"> 
    <meta property="og:url"                          content="http://photography-mapped.com/interact.html"> 
    <meta property="og:image"                        content="http://photography-mapped.com/img/interactive/IntroAnimation.gif"> 
    <meta property="og:image:width"                  content="750"> 
    <meta property="og:image:height"                 content="375"> 
    <meta property="og:image:type"                   content="image/gif"> 
    <meta property="og:site_name"                    content="Photography Mapped"> 
    
    <link rel="icon" type="image/png" href="img/flavicon.png" />
    <link rel="stylesheet" type="text/css" href="stylesheets/screen.css?v=0.3.6.6">
    <meta name="viewport" content="width=device-width">
    
    <!-- Facebook Pixel Code -->
    <script>
    !function(f,b,e,v,n,t,s){if(f.fbq)return;n=f.fbq=function(){n.callMethod?
    n.callMethod.apply(n,arguments):n.queue.push(arguments)};if(!f._fbq)f._fbq=n;
    n.push=n;n.loaded=!0;n.version='2.0';n.queue=[];t=b.createElement(e);t.async=!0;
    t.src=v;s=b.getElementsByTagName(e)[0];s.parentNode.insertBefore(t,s)}(window,
    document,'script','https://connect.facebook.net/en_US/fbevents.js');
    fbq('init', '1821111268143620'); // Insert your pixel ID here.
    fbq('track', 'PageView');
    </script>
    <noscript><img height="1" width="1" style="display:none"
    src="https://www.facebook.com/tr?id=1821111268143620&ev=PageView&noscript=1"
    /></noscript> <!-- End Facebook Pixel Code -->
    
</head>

<body>

<header>
    <hgroup>
        <a href="index.html"><svg id="logo" width="100" height="34"></svg></a>
        <h1><a href="index.html">Photography Mapped</a></h1>
    </hgroup>
    <nav style="padding-bottom: 7px;">
        <ul>
            <li><a href="interact.html" class="nav-active">Interact</a></li>
            <li><a href="print.html">Graphic</a></li>
            <li><a href="about.html">About</a></li>
        </ul>
    </nav>
    <section id="share">
        <p><a href="https://twitter.com/intent/tweet?text=www.photography-mapped.com" target="_blank">tweet</a> / <a href="https://www.facebook.com/sharer/sharer.php?u=http%3A%2F%2Fwww.photography-mapped.com%2F&amp;src=sdkpreparse">fb</a></p>
    </section>
</header>

<div id="camera-settings">
   <form>
       <p>- 
        <span class="rd_auto rd"><input id="rd_auto" class="vis-hidden" type="radio" name="setting" value="auto"><label for="rd_auto">Auto</label></span> / 
        <span class="rd_manual rd"><input id="rd_manual" class="vis-hidden" type="radio" name="setting" value="manual" checked><label for="rd_manual">Manual</label></span>
<!--        <span class="rd_apert rd" hidden><input id="rd_apert" class="vis-hidden" type="radio" name="setting" value="apert"><label for="rd_apert">Aperture Priority</label></span>-->
<!--        <span class="rd_shutt rd" hidden><input id="rd_shutt" class="vis-hidden" type="radio" name="setting" value="shutt"><label for="rd_shutt">Shutter Priority</label></span>-->
         -</p>
    </form>
</div>
        
<section id="interact-illus">
    <div class="centre">
        <svg id="paper" width="100%" viewBox="0 50 1200 300">
            <filter id="blurMe" x="0" y="0" color-interpolation-filters="sRGB">
                <feGaussianBlur id="filterBlur" in="SourceGraphic" stdDeviation="5" result="blur"/>
            </filter>
            <filter id="blurHeli" x="0" y="0" color-interpolation-filters="sRGB">
                <feGaussianBlur id="filterBlurHeli" in="SourceGraphic" stdDeviation="0" result="blur"/>
            </filter>
        </svg>
    </div>
</section>


<article id="interactContent">
       
        <section class="hidden" id="take-photo">
            <div class="group">
               <div class="one"></div>
                <div class="two hide">
                    <p>1. Adjust settings</p>
                </div>
                <div class="two hide">
                    <p>2. Observe changes</p>
                </div>
                <div class="two">
                    <form>
                        <button type="button" id="takePhoto" style="width: 100%;"><span class="hide">3.</span> Take Photo</button>
                    </form>
                </div>
                <div class="one"></div>
            </div>
        </section>

        <section class="hidden" id="rangefinders">
            <div class="group">
                <div class="one active light" >
                    <h1>Light</h1>
                    <input type="range" id="test" class="range" min="-4" max="16" value="7"/>
                </div>
                <div class="one active apert">
                    <h1>Aperture</h1>
                    <input type="range" class="range" min="0" max="8" value="4"/>
                </div> 
                <div class="one active shutt">
                    <h1>Shutter</h1>
                    <input type="range" class="range" min="0" max="14" value="6"/>
                </div>
                <div class="one active senso">
                    <h1>Sensor</h1>
                    <input type="range" class="range" min="0" max="8" value="4"/>
                </div>
                <div class="one expos" style="position: relative;">
                    <h1>Exposure</h1>
                    <input type="range" class="range" min="-5" max="5" value="0" disabled/>
                    <div id="exposureMarker"></div>
                </div>
            </div>
        </section>

        <section class="hidden" id="measure">
            <div class="group">
                <div class="one active light" >
                    <h3 class="hide">Example</h3>
                    <p class="prev hide"></p>
                    <p class="number hide"></p>
                    <p class="describe hide"></p>
                </div>
                <div class="one active apert">
                    <h3>F/Number</h3>
                    <p class="prev hide"></p>
                    <p class="number"></p>
                    <p class="describe hide"></p>
                </div> 
                <div class="one active shutt">
                    <h3><span class="hide">Shutter</span> Speed</h3>
                    <p class="prev hide"></p>
                    <p class="number"></p>
                    <p class="describe hide"></p>
                </div>
                <div class="one active senso">
                    <h3>ISO</h3>
                    <p class="prev hide"></p>
                    <p class="number"></p>
                    <p class="describe hide"></p>
                </div>
                <div class="one inactive expos" style="position: relative;">
                    <h3><span class="hide">Exposure</span> Meter</h3>
                    <p class="prev hide"></p>
                    <p class="number"></p>
                    <p class="describe hide"></p>
                    <p class="hint">Recommended Exposure</p>
                    <div id="mode-describe" hidden>
                        <p id="auto-describe" class="info" hidden>In AUTO, settings automatically update to conpensate for lack or abundance of light.<br><br>This means the camera will make its best guess of the exposure needed to get the right image brightness.</p>
                        <p id="manual-describe" class="info">When in MANUAL, you need to be aware of how adjusting settings is affecting exposure.<br><br>An Exposure Meter (above) offers guidence. The middle of the meter represents the exposure the camera recommends.</p>
                    </div>
                </div>
            </div>
        </section>

        <section class="hidden" id="second-effect">
            <div class="group">
                <div id="effect-change-light" class="one active light">
                </div>
                <div id="effect-change-apert" class="one active apert">
                    <h3>Depth of Field</h3>
                    <svg class="illusNew" id="effectApertSVG" width="100%" viewBox="0 0 100 40">
                        <filter id="blurDOF">
                            <feGaussianBlur id="dofFilterBlur" in="SourceGraphic" stdDeviation="5" />
                        </filter>
                    </svg>
                    <p class="describe hide"></p>
                </div> 
                <div id="effect-change-shutt" class="one active shutt">
                    <h3>Motion Blur</h3>
                    <svg class="illusNew" id="effectShuttSVG" width="100%" viewBox="0 0 200 80"></svg>
                    <p class="describe hide"></p>
                </div>
                <div id="effect-change-senso" class="one active senso">
                    <h3>Image Noise</h3>
                    <svg class="illusNew" id="effectSensoSVG" width="100%" viewBox="0 0 200 80"></svg>
                    <p class="describe hide"></p>
                </div>
                <div id="effect-change-expos" class="one inactive expos">
                </div>
            </div>
        </section>
        
        <section class="hidden" id="expos-effect">
            <div class="group">
                <div class="one active light" >
                    <h3>Exposure Effect</h3>
                    <p class="small hide">Light available</p>
                    <p class="number"></p>
                    <p class="describe hide"></p>
                </div>
                <div class="one active apert">
                    <h3>Exposure Effect</h3>
                    <p class="small hide">light in; volume</p>
                    <p class="number"></p>
                    <p class="describe hide"></p>
                </div> 
                <div class="one active shutt">
                    <h3>Exposure Effect</h3>
                    <p class="small hide">Light in; time</p>
                    <p class="number"></p>
                    <p class="describe hide"></p>
                </div>
                <div class="one active senso">
                    <h3>Exposure Effect</h3>
                    <p class="small hide">Light needed</p>
                    <p class="number"></p>
                    <p class="describe hide"></p>
                </div>
                <div class="one inactive expos">
                </div>
            </div>
        </section>
    
	    <section id="mobile-info" class="show">
	        <h3>On a small screen?</h3>
            <p>This is a reduced version
            <br>(it still works there's just less info).
            <br>&nbsp;
            <br>To see more:
            <br>try flipping your screen into landscape,
            <br>or email yourself a link to look at later...</p>
	        <p style="margin:15px;"><a href="mailto:?subject=Interactive%20Camera%20Tool%20(by%20Photography%20 Mapped)&amp;body=http://photography-mapped.com/interact.html">CLICK TO EMAIL</a></p>
	    </section>
	</article>
   
<footer>
   <section id="footerContent" class="group">
        <div class="one hide" style="left: 20px; padding-top: 70px;">
            <p class="small">
                <a href="mailto:info@photography-mapped.com">info@photography-mapped.com</a>
            </p>
        </div>
        <div class="one">
             <section id="mc_embed_signup">
                <form action="//photography-mapped.us14.list-manage.com/subscribe/post?u=58a5ff0247715345e9768e1a6&amp;id=b992f7a233" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
                    <div id="mc_embed_signup_scroll">
                        <input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="" required>
                        <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
                        <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_58a5ff0247715345e9768e1a6_b992f7a233" tabindex="-1" value=""></div>
                        <div class="clear"><input type="submit" value="Subscribe &rarr;" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
                    </div>
                </form>
                <p style="color:grey;">I hope to produce new tools in the future &mdash; add your email for the occasional update.</p>
            </section>
        </div>
        <div class="one hide">
            <p style="right: 20px; text-align:right; padding-top: 70px;" class="small"><a href="https://docs.google.com/a/photography-mapped.com/forms/d/e/1FAIpQLSeG6NCo9HA17lFA-xJYCRfVJu2sfUxp1HIex0NyPUQ8MFs-9w/viewform">Give Feedback</a> | &copy; 2016 <a href="http://www.simonroberts.co.uk">Simon Roberts</a></p>
        </div>
    </section>
</footer>


<script src="js/jquery-3.1.1.min.js"></script>
<script src="js/fotorama.js"></script>
<script src="js/snap.svg.js"></script>
<script src="js/logo-svg.js"></script>
<script src="js/jquery.color.js"></script>
<script src="js/interact-main.js"></script>
<script src="js/interact.js"></script>
<script src="https://use.typekit.net/aja3dwx.js"></script>
<script>try{Typekit.load({ async: true });}catch(e){}</script>
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');
  ga('create', 'UA-87945752-1', 'auto');
  ga('send', 'pageview');
</script>
<script type="text/javascript">
/* <![CDATA[ */
var google_conversion_id = 866358799;
var google_custom_params = window.google_tag_params;
var google_remarketing_only = true;
/* ]]> */
</script>
<script type="text/javascript" src="//www.googleadservices.com/pagead/conversion.js">
</script>
<noscript>
<div style="display:inline;">
<img height="1" width="1" style="border-style:none;" alt="" src="//googleads.g.doubleclick.net/pagead/viewthroughconversion/866358799/?guid=ON&amp;script=0"/>
</div>
</noscript>
</body>
</html>
