# Tabs 选项卡切换

选项卡切换组件。

### 何时使用

用户需要通过平级的区域将大块内容进行收纳和展现，保持界面整洁。

### 基本用法

:::demo

```vue
<template>
  <d-tabs type="tabs" v-model="id">
    <d-tab id="tab1" title="Tab1" tabId="tab1">
      <p>Tab1 Content</p>
    </d-tab>
    <d-tab id="tab2" title="Tab2" tabId="tab2">
      <p>Tab2 Content</p>
    </d-tab>
    <d-tab id="tab3" title="Tab3" tabId="tab3">
      <p>Tab3 Content</p>
    </d-tab>
  </d-tabs>
</template>
<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const id = ref('tab1');
    return {
      id
    };
  }
});
</script>
```

:::

### Pills 类型

:::demo

```vue
<template>
  <d-tabs type="pills" v-model="id">
    <d-tab id="tab1" title="Tab1" tabId="tab1">
      <p>Tab1 Content</p>
    </d-tab>
    <d-tab id="tab2" title="Tab2" tabId="tab2">
      <p>Tab2 Content</p>
    </d-tab>
    <d-tab id="tab3" title="Tab3" tabId="tab3">
      <p>Tab3 Content</p>
    </d-tab>
  </d-tabs>
</template>
<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const id = ref('tab1');
    return {
      id
    };
  }
});
</script>
```

:::

### Options 类型

:::demo

```vue
<template>
  <d-tabs type="options" v-model="id">
    <d-tab id="tab1" title="Tab1" tabId="tab1">
      <p>Tab1 Content</p>
    </d-tab>
    <d-tab id="tab2" title="Tab2" tabId="tab2">
      <p>Tab2 Content</p>
    </d-tab>
    <d-tab id="tab3" title="Tab3" tabId="tab3">
      <p>Tab3 Content</p>
    </d-tab>
  </d-tabs>
</template>
<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const id = ref('tab1');
    return {
      id
    };
  }
});
</script>
```

:::

### Wrapped 类型

:::demo

```vue
<template>
  <d-tabs type="wrapped" v-model="id">
    <d-tab id="tab1" title="Tab1" tabId="tab1">
      <p>Tab1 Content</p>
    </d-tab>
    <d-tab id="tab2" title="Tab2" tabId="tab2">
      <p>Tab2 Content</p>
    </d-tab>
    <d-tab id="tab3" title="Tab3" tabId="tab3">
      <p>Tab3 Content</p>
    </d-tab>
  </d-tabs>
</template>
<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const id = ref('tab1');
    return {
      id
    };
  }
});
</script>
```

:::

### Slider 类型

:::demo

```vue
<template>
  <d-tabs type="slider" v-model="id">
    <d-tab id="tab1" title="Tab1" tabId="tab1">
      <p>Tab1 Content</p>
    </d-tab>
    <d-tab id="tab2" title="Tab2" tabId="tab2">
      <p>Tab2 Content</p>
    </d-tab>
    <d-tab id="tab3" title="Tab3" tabId="tab3">
      <p>Tab3 Content</p>
    </d-tab>
  </d-tabs>
</template>
<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const id = ref('tab1');
    return {
      id
    };
  }
});
</script>
```

:::

### 禁用选项卡

:::demo

```vue
<template>
  <d-tabs type="tabs" v-model="id">
    <d-tab id="tab1" title="Tab1" tabId="tab1" :disabled="true">
      <p>Tab1 Content</p>
    </d-tab>
    <d-tab id="tab2" title="Tab2" tabId="tab2">
      <p>Tab2 Content</p>
    </d-tab>
    <d-tab id="tab3" title="Tab3" tabId="tab3">
      <p>Tab3 Content</p>
    </d-tab>
  </d-tabs>
</template>
<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const id = ref('tab2');
    return {
      id
    };
  }
});
</script>
```

:::

### 拦截 tab 切换

:::demo

```vue
<template>
  <d-tabs
    type="tabs"
    v-model="id"
    :beforeChange="beforeChange"
    @activeTabChange="activeTabChange"
  >
    <d-tab id="tab1" title="Tab1" tabId="tab1">
      <p>Tab1 Content</p>
    </d-tab>
    <d-tab id="tab2" title="Tab2" tabId="tab2">
      <p>Tab2 Content</p>
    </d-tab>
    <d-tab id="tab3" title="Tab3" tabId="tab3">
      <p>Tab3 Content</p>
    </d-tab>
  </d-tabs>
</template>
<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const id = ref('tab3');
    const beforeChange = (tab) => {
      if (tab === 'tab1') {
        id.value = 'tab2';
        return false;
      } else {
        return true;
      }
    };
    const activeTabChange = (id) => {
      console.log(id, 'activeTabChange');
    };
    return {
      id,
      beforeChange,
      activeTabChange
    };
  }
});
</script>
```

:::

### 自定义模板

:::demo

```vue
<template>
  <d-tabs type="tabs" v-model="id">
    <d-tab id="tab1" title="Tab1" tabId="tab1">
      <template v-slot:dTabTitle> 就是这样 </template>
      <p>Tab1 Content</p>
    </d-tab>
    <d-tab id="tab2" title="Tab2" tabId="tab2">
      <template v-slot:dTabTitle> 就是这样1 </template>
      <p>Tab2 Content</p>
    </d-tab>
    <d-tab id="tab3" title="Tab3" tabId="tab3">
      <template v-slot:dTabTitle> 就是这样2 </template>
      <p>Tab3 Content</p>
    </d-tab>
  </d-tabs>
</template>
<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const id = ref('tab3');
    return {
      id
    };
  }
});
</script>
```

:::

### API

|     参数     |                      类型                       |  默认  |                                                 说明                                                  |     |
| :----------: | :---------------------------------------------: | :----: | :---------------------------------------------------------------------------------------------------: | --- |
|     type     | `tabs \| pills \| options \| wrapped \| slider` | 'tabs' |                                         可选，选项卡组的类型                                          |
| showContent  |                    `boolean`                    |  true  |                                    可选，是否显示选项卡对应的内容                                     |
|   v-model    |                    `string`                     |   --   |                                可选，当前激活的选项卡，值为选项卡的 id                                |
| customWidth  |                    `string`                     |   --   |                                        可选，自定义选项卡的宽                                         |
|   vertical   |                    `boolean`                    | false  |                                           可选，是否垂直显                                            |
| beforeChange |               `function\|Promise`               |   --   |                tab 切换前的回调函数,返回 boolean 类型，返回 false 可以阻止 tab 的切换                 |
| reactivable  |                    `boolean`                    | false  | 可选，点击当前处于激活态的 tab 时是否触发`activeTabChange`事件，`true`为允许触发，`false`为不允许触发 |

### d-tabs 事件

|      参数       |            类型            | 说明                                                |
| :-------------: | :------------------------: | :-------------------------------------------------- |
| activeTabChange | `function(string\|number)` | 可选，选项卡切换的回调函数，返回当前激活选项卡的 id |

### d-tab 参数

|   参数   |       类型       | 默认  | 说明                                   |
| :------: | :--------------: | :---: | :------------------------------------- |
|    id    | `number\|string` |  --   | 可选，选项卡的 id 值, 需要设置为唯一值 |
|  title   |     `string`     |  --   | 可选，选项卡的标题                     |
| disabled |    `boolean`     | false | 可选，选项卡是否不可用                 |