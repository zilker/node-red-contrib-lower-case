# node-red-contrib-lower-case

This is an example of Node-RED editor hooks using in browser

```html
<script type="text/javascript">
    RED.hooks.add("preDeploy",  (event, done) => {
        setTimeout(() => {
            console.log('preDeploy client hook');
            event.test = 1;
            console.log(event);
            // Sending false is canceling the deploy process
            done(false);
        }, 2000)
    });

    RED.hooks.add("postDeploy",  (event, done) => {
        console.log('postDeploy client hook');
        console.log(event);
        done();
    });

    RED.hooks.add("onDrop",  (event, done) => {
        console.log('onDrop client hook');
        event.test = 1;
        console.log(event);
        done();
    });
</script>
```
