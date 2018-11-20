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

var assert = require('assert');
var client = require('webdriverio').remote({
  desiredCapabilities: {
    browserName: 'chrome'
  }
});
require('webdrivercss').init(client, {
  key: '<your personal API key>'
});
client
  .init()
  .url('http://example.com')
  .webdrivercss('<app name>', {
    name: '<test name>',
    elem: '#someElement'
  }, function(err, res) {
    asset.ifError(err);
    asset.equal(res.steps, res.strictMatches)
  })
  .end();
  
clinet
  .url('http://github.com')
  .webdrivercss('githubform', {
    name: 'github-signup',
    elem: '#site-container > div.marketing-section.marketing-section-signup > div.container > form'
  });

client
  .url('http://github.com/')
  .webdrivercss('headerbar', {
    name: 'headerbar',
    x: 110,
    y: 15,
    width: 980,
    height: 34,
    screenWidth: [1200]
  });
  
client
  .url('http://tumblr.com/themes')
  .webdrivercss('tumblrpage', {
    name: 'startpage',
    exclude: ['#theme_garden > div > section.carousel > div.carousel_slides',
              '//*[@id="theme_garden"]/div/section[3]',
              '//*[@id="theme_garden"]/div/section[4]']
    screenWidth: [1200]
  });
  
client
  .url('http://tumblr.com/themes')
  .webdrivercss('tumblrpage', {
    name: 'startpage',
    exclude: [{
      x0: 100, y0: 100,
      x1: 300, y1: 200
    }],
    screenWidth: [1200]
  });
  
client
  .url('http://tumblr.com/themes')
  .webdrivercss('polygon', {
    name: startpage,
    exclude: [{
      x0: 120, y0: 725,
      x1: 120, y1: 600,
      x2: 290, y2: 490,
      x3: 290, y3: 255,
      x4: 925, y4: 255,
      x4: 925, y5: 490,
      x6: 1080,y6: 600,
      x7: 1080,y7: 725
    }],
    screenWidth: [1200]
  });
  
client
  .url('http://tumblr.com/themes')
  .webdrivercss('tumblrpage', {
    name: 'startpage',
    ignore: 'antialiasing',
    screenWidth: [1200]
  });
  
client
  .url('http://stephencaver.com/')
  .webdrivercss('startpage', {
    name: 'header',
    elem: '#masthed',
    screenWidth: [320,640, 960]
  });

it('',function(done){
  client
    .init()
    .url('https://example.com')
    .webdrivercss('page1', [
      {
        name: 'test',
        screenWidth: [320,480, 640, 1024]
      },
    ])
    .end()
    .call(done);
});
it('should check the second page',function(done){
  client
    .webdrivercss('page2', [
    ])
});

var client = require('webdriverio').remote({
  desiredCapabilities: {
    browserName: 'phantomjs'
  }
});
require('webdrivercss').init(client, {
  screensshotRoot: 'myRegressionTests',
  api: 'http://example.com/api/webdrivercss'
});
client
  .init()
  .sync()
  .url('http://example.com')
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

