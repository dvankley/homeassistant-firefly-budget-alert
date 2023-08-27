# Home Assistant Firefly Budget Alerts

# Goal
My spouse asked me the other day if I could set up real-time notifications for our Firefly III
budget status. As a satisfied user of both Firefly III and Home Assistant, a combination of the two seemed
like a natural fit, given Firefly's extensive API and Home Assistant's flexible notification capability
via the companion app.

Turns out it's not hard to accomplish the goal via a Node-RED flow.

# Setup
1. Import `flow.json` into your Home Assistant Node-RED as a new flow.
2. Set the [global context value](https://nodered.org/docs/user-guide/context) `fireflyUrl` in your Node-RED config
to the base URL of your Firefly install, i.e. `https://firefly.example.com`.
3. Set up a `localfilesystem` context storage module named `store` in your Node-RED config, for instance as below:
   1. You can name it something other than `store`, but then you need to replace all the references in `flow.json`.
```javascript
  contextStorage: {
    store: { module: "localfilesystem"},
    default: { module: "memory" }
  },

```

4. Profit.