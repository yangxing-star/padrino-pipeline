
#padrino-assets
This is an early version and work in progress for sprockets + padrino pipeline

include in your padrino project
```ruby
gem 'padrino-assets', :github => 'Ortuna/padrino-assets'
```

```ruby
module Ortuna
  class App < Padrino::Application
    register Padrino::Rendering
    register Padrino::Mailer
    register Padrino::Helpers
    register Padrino::Assets

    configure_assets do |assets|
      assets.append_path 'assets/javascripts' # defaults to assets/javascript
      assets.append_path 'assets/stylesheets' # defaults to assets/javascript
      assets.js_prefix = '/custom/location'   # defaults to /assets/javascripts
      assets.css_prefix = '/custom/stylesheets'   # defaults to /assets/javascripts
    end
  end
end
```

visit `http://localhost:3000/custom/location/app.js` will map to the file
app/assets/javascripts/app.js

visit `http://localhost:3000/custom/stylesheets/main.css` will map to the file
app/assets/stylesheets/main.css

use sprockets helpers like you would:
```javascript
//= require stuff
function stuff() {

}
```
