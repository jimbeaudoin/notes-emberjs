# Pods

# OLD NOTES. WARNING!

##### Remove folders if needed.
```sh
cd app
rm -rf templates controllers routes views
# If you put everything in pods
rm -rf components/ controllers/ models/ routes/ templates/ views/
```

##### Set Default to Pods in `.ember-cli`
```sh
"usePods": true
```

##### In `config/environment.js`
```sh
podModulePrefix: 'frontend/pods',
```

##### Pods Structure
```sh
app/pods/application/template.hbs
app/pods/users/model.js
app/pods/users/route.js
app/pods/users/controller.js
# Supported Blueprints
adapter
component
controller
model
route
resource
serializer
template
transform
view
```
