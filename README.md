# wct-atom-snippet
web-component-test snippet for Atom

```
'.text.html.basic':
  'WCT Component Tests':
    'prefix': 'testwct'
    'body': """
    <!doctype html>
    <html lang="en">
      <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, minimum-scale=1, initial-scale=1, user-scalable=yes">

        <title>${1:COMPONENT-NAME} test</title>

        <script src="../../../webcomponentsjs/webcomponents-loader.js"></script>
        <script src="../../../web-component-tester/browser.js"></script>

        <link rel="import" href="../../src/YOUR-PATH/${1:COMPONENT-NAME}.html">
      </head>
      <body>

        <test-fixture id="Baby">
          <template>
            <my-kid></my-kid>
          </template>
        </test-fixture>
${2:
        <test-fixture id="Boy">
          <template>
            <my-kid birthday="16-03-1995"></my-kid>
          </template>
        </test-fixture>
}
        <script>
          suite('${1:COMPONENT-NAME}', () => {
            let element;
            setup(() => {
              element = fixture('Baby');
            });

            /**
             * Test default properties
             */
            test('aka baby-test', () => {
              assert.equal(element.birthday, '01-01-1970');
            });
${2:
            /**
             * Test properties assignments
             */
            test('with properties assignments', () => {
              assert.equal(element.birthday, '01-01-1970');
            \\});
}
          });
        </script>

      </body>
    </html>
    """
```
