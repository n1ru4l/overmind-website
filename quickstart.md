# Quickstart

From the command line install the Overmind package:

{% tabs %}
{% tab title="React" %}
```
npm install overmind overmind-react
```
{% endtab %}

{% tab title="Vue" %}
```
npm install overmind overmind-vue
```
{% endtab %}

{% tab title="Angular" %}
```text
npm install overmind overmind-angular
```
{% endtab %}
{% endtabs %}

### Setup

Now set up a simple application like this:

{% tabs %}
{% tab title="overmind/state.js" %}
```javascript
export const state = {
  title: 'My App'
}
```
{% endtab %}

{% tab title="overmind/index.ts" %}
```typescript
import { state } from './state'

export const config = {
  state
}
```
{% endtab %}
{% endtabs %}

And fire up your application in the browser or whatever environment your user interface is to be consumed in by the users.

### VS Code

For the best experience you should install the [OVERMIND DEVTOOLS](https://marketplace.visualstudio.com/items?itemName=christianalfoni.overmind-devtools-vscode) extension. This will allow you to work on your application without leaving the IDE at all.

![](.gitbook/assets/amazing_devtools.png)

{% hint style="info" %}
If you are using the **Insiders** version of VSCode the extension will not work. It seems to be some extra security setting.
{% endhint %}

### Devtool app

Alternatively you can install the standalone application of the devtools. It is highly recommended to install the package [CONCURRENTLY](https://www.npmjs.com/package/concurrently). It allows you to start the devtools as you start your build process:

```text
npm install overmind-devtools concurrently
```

{% code title="package.json" %}
```javascript
{
  ...
  "scripts": {
    "start": "concurrently \"overmind-devtools\" \"someBuildTool\""
  },
  ...
}
```
{% endcode %}

### Hot Module Replacement <a id="quickstart-hot-module-replacement"></a>

A popular concept introduced by Webpack is [HMR](https://webpack.js.org/concepts/hot-module-replacement/). It allows you to make changes to your code without having to refresh. Overmind automatically supports HMR. That means when **HMR** is activated Overmind will make sure it updates and manages its state, actions and effects. Even the devtools will be updated as you make changes.

