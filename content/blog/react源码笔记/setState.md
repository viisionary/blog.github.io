---
title: react 源码阅读 - setState
date: 2021-04-02
categories : ["react","源码"]
tags: ["react","源码"]
---

setState 的源码分析

<!--more-->


```typescript
Component.prototype.setState = function (partialState, callback) {
    this.updater.enqueueSetState(this, partialState, callback, 'setState');
};

```

```typescript

function enqueueSetState(inst, payload, callback) {
    // ...
    // 存在来updatel里
    update.payload = payload;
    // 将update插入updateQueue 
    // 调度update
    enqueueUpdate(fiber, update, lane);
    scheduleUpdateOnFiber(fiber, lane, eventTime);
}

```
