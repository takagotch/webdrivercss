### webdrivercss
---
https://github.com/webdriverio-boneyard/webdrivercss

```sh
npm install -g selenium-standalone
selenium-standalone install
selenium-standalone start

brew install graphicsmagick
sudo apt-get install graphicsmagick

npm install webdrivercss
npm install webdriverio

npm install -g http-server
http-server -p 8080
```

```js
var assert = require('assert');
var client = require('webdriverio').remote({desiredCapabilities:{browserName: 'chrome'}})
require('webdrivercss').init(client);
client
  .init()
  .url('http://example.com')
  .webdrivercss('startpage',[
    {
      name: 'header',
      elem: '#header'
    },{
      name: 'hero',
      elem: '//*[@id="hero"]/div[2]'
    }
  ], function(err, res){
    assert.ifError(err);
    assert.ok(res.header[0].isWithinMisMatchTolerance);
    assert.ok(res.hero[0].isWithMisMatchTolerance)
  })
  .end();
  
var client = require('webdriverio').remote({
  desiredCapabilities: {
    browserName: 'phantomjs'
  }
}).init();
require('webdrivercss').init(client, {
  screenshotRoot: 'my-shots',
  falledComparisonsRoot: 'diffs',
  misMatchTolerance: 0.05,
  screenWidth: [320,480, 640, 1024]
});

var assert = require('assert');
describe('my website should always look the same', function(){
  it('header should always look the same', function(){
    client
      .url('http://www.example.org')
      .webdrivercss('header', {
        name: 'header',
        elem: '#header'
      }, function(err,res){
        assert.ifError(err);
        assert.ok(res.header[0].isWithinMisMatchTolerance)
      })
      .call(done);
  });
});

var assert = require();
var client = require().remote();
require().init();
client
  .init()
  .url()
  .webdrivercss()
  .end();

client
  .url()
  .webdrivercss();
  
client
  .url()
  .webdrivercss();
  
client
  .url()
  .webdrivercss();
  
client
  .url()
  .webdrivercss();
  
client
  .url ()
  .webdrivercss();
  
client
  .url()
  .webdrivercss();
  
client
  .url()
  .webdrivercss();

it();
it();

var client = require().remote();
require().init();
client
  .init()
  .sync()
  .url()
  .sync()
  .end();
```

```
{
  header: [
    {
      baselinePath: 'webdrivercss/header.header.baseline.png',
      message: 'mismatch tolerance not exceeded (~0), baseline didn\'t change',
      misMatchPercentage: 0,
      isExactSameImage: true,
      isSameDimensions: true,
      isWithinMisMatchTolerance: true
    }
  ]
}
```

