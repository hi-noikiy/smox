<p align="center"><img src="http://ww1.sinaimg.cn/large/85564debgy1froiubji5aj207f03nq34.jpg" alt="smox logo"></p>

[![NPM version](https://img.shields.io/npm/v/smox.svg?style=flat)](https://npmjs.com/package/smox)
[![NPM downloads](https://img.shields.io/npm/dm/smox.svg?style=flat)](https://npmjs.com/package/smox)

# smox

> Just 1kB state management based on New context api which has similar but simple api with Redux (or Vuex).

## start

p.s.不知为啥npm发布不了，所以以下安装没用，准备明天再试试

```shell
yarn add smox
```

or

```shell
npm i smox
```

## use

```javascript
import React from 'react'
import ReactDOM from 'react-dom'
import App from './app.js'
import { Store, Provider } from 'smox'

const state = {
  count: 2
}

const actions = {
  add(state) {
    return {
      count: state.count + 1
    }
  },
  cut(state) {
    return {
      count: state.count - 1
    }
  }
}

const store = new Store({ state, actions })

ReactDOM.render(
  <Provider value={store}>
    <App />
  </Provider>,
  document.getElementById('root')
)
```
then 
```javascript
import React from 'react'
import { withStore } from 'smox'

@withStore
class App extends React.Component {
  render() {
    return (
      <div>
        <h1>Now:{this.props.count}</h1>
        <button onClick={this.props.add}>ADD+</button>
      </div>
    )
  }
}

export default App
```

# API
* store.state
* store.actions
* store.dispatch(action)
* store.subscribe(sub)

* withStore

## demo(last verson)

* [Counter](https://github.com/132yse/smox-counter)
* [爱弹幕后台](https://github.com/132yse/idanmu-admin)

# about

* blog: [伊撒尔の窝](http://www.yisaer.com)
* weibo: [@世界倒数第一公主殿下](http://weibo.com/oreshura)
