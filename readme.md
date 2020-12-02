# @bytesoftio/isolate

## Installation

`yarn add @bytesoftio/isolate` or `npm install @bytesoftio/isolate`

## Table of contents

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Description](#description)
- [Usage](#usage)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Description

This package provides a tiny component `Isolate` that allows you to isolate other components from unnecessary re-renders.

## Usage

Take this component for example, the children of the `Isolate` component will only re-render when the `observedValue` changes. Changes to the `ignoredValue` will not lead to re-renders of the isolated children.

```tsx
import React, { useState } from "react"
import { Isolate } from "@bytesoftio/isolate"

const Component = () => {
  const [ignoredValue, setIgnoredValue] = useState(0)
  const [observedValue, setObservedValue] = useState(0)

  return (
    <div>
      <h1>ignored value: {ignoredValue}</h1>

      <Isolate deps={[observedValue]} showRenders>
        <h2>ignored value: {ignoredValue}</h2>
        <h2>observed value: {observedValue}</h2>
      </Isolate>
    </div>
  )
}
```


