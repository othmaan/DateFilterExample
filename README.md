# DateFilterExample
 angularjs date filter example!


```javascript
var MyApp = angular.module('YOUR_APP_NAME', []);

MyApp.filter('formatSecondsToMMSS', function () {
    return function (timeInSeconds) {
        if (isNaN(timeInSeconds) === false) {
            var s, m, h;
            s = Math.floor(timeInSeconds);

            m = Math.floor(s / 60);
            s = s % 60;
            
            h = Math.floor(m / 60);
            m = m % 60;
            
            //d = Math.floor(h / 24);
            //h = h % 24;

            s = appendZero(s);
            m = appendZero(m);
            h = appendZero(h);
            //d = appendZero(d);
            
            if (timeInSeconds < 3600) {
                return (m + ":" + s);
            } else if (timeInSeconds >= 3600) {
                return (h + ":" + m + ":" + s);
            }
        };
    }
    function appendZero(n){
        return (n < 10 ? "0"+n : n);
    }
})
```
