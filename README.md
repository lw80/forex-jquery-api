Forex-jquery-api
==============================

Forex data feed API example in <strong>jQuery</strong>. 
<br/>For pure javascript example without jquery visit <a href="https://github.com/OndrejKuchta/forex-javascript-api">forex-javascrip-api</a>

<br/>This example is about using <a href="http://apirates.com/">Apirates.com</a> Forex API in <strong>jQuery</strong> web application.
<a href="http://apirates.com/">Apirates.com</a> provides access to Forex, Stocks and Commodity live data through JSONP format .

<br/>JSONP API:

For the current bar:

<code><a href="http://api.apirates.com/jsonp/update?callback=myCallback">http://api.apirates.com/jsonp/update?callback=myCallback</a></code>

For history bars:

<code><a href="http://api.apirates.com/jsonp/history/M1?callback=myCallback">http://api.apirates.com/jsonp/history/M1?callback=myCallback</a></code>
<code><a href="http://api.apirates.com/jsonp/history/M5?callback=myCallback">http://api.apirates.com/jsonp/history/M5?callback=myCallback</a></code>
<code><a href="http://api.apirates.com/jsonp/history/M10?callback=myCallback">http://api.apirates.com/jsonp/history/M10?callback=myCallback</a></code>
<code><a href="http://api.apirates.com/jsonp/history/M15?callback=myCallback">http://api.apirates.com/jsonp/history/M15?callback=myCallback</a></code>
<code><a href="http://api.apirates.com/jsonp/history/M30?callback=myCallback">http://api.apirates.com/jsonp/history/M30?callback=myCallback</a></code>
<code><a href="http://api.apirates.com/jsonp/history/M60?callback=myCallback">http://api.apirates.com/jsonp/history/M60?callback=myCallback</a></code>


<strong>How JSONP works with jQuery?</strong>

JSONP with jQuery is very simple. Just add this url to AJAX call and set "dataType:jsonp"
```
url: 'http://api.apirates.com/jsonp/update',
```

After success the function is called and the "data" parameter will contain current Forex data.
```
$(document).ready(function(){
                $.ajax({
                    url: 'http://api.apirates.com/jsonp/update',
                    dataType: 'jsonp',
                    success: function(data){
                        
                        $('#ForexFeed').html(JSON.stringify(data));
                    }
                });
            })
```




