# notes-emberjs
Ember.js Notes for Myself

## Installation via ember-cli
```sh
npm install -g ember-cli
npm install -g bower
npm install -g phantomjs
```
## New Application Creation
```sh
ember new my-new-app
cd my-new-app
ember serve
```
## Pods
Remove unnecessary folders.
```sh
cd app
rm -rf templates controllers routes views
# Put everything in pods
rm -rf components/ controllers/ models/ routes/ templates/ views/
```
Set Default to Pods in `.ember-cli`
```sh
"usePods": true
```

--
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons Licence" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/80x15.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">notes-emberjs</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="http://jim-beaudoin.com" property="cc:attributionName" rel="cc:attributionURL">Jimmy Beaudoin</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.
