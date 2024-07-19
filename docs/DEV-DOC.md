# 移植开发文档

## 样式 stylus

`stylus -w templates/assets/css/styl/main.styl -o templates/assets/css/main.css -w`  
`stylus templates/assets/css/styl/main.styl -o templates/assets/css/main.css`  

源文件注释部分，`hexo-config()`注入点替换成`hexo _config.yml`原始参数，以便通过编译  
see https://theme-next.js.org/docs/theme-settings/  

### 注入参数重写对应表

| hexo stylus |   | halo setting.yaml |   |
|-------------|---|-------------------|---|
|             |   |                   |   |


## 开发状态标识

|     |      |   |
|-----|------|---|
| hud | 未做   |   |
| hde | 已完成  |   |
| hdi | 正在做  |   |
| huk | 未知   |   |
| hpt | 部分完成 |   |

- 未做
- 正在做
- 部分完成
- 完成

- 来源不详

- 未填充
- 临时填充

## 模板设置项对应表

|   next setting.yaml    |         |                   halo setting.yaml group                    |         备注          |
|:----------------------:|---------|:------------------------------------------------------------:|:-------------------:|
|         主题基础设置         |         |                            主题基础设置                            |       主体基础设置        |
|                        |         |        `${theme.config.theme_setting.author[0].name}`        |        用户昵称         |
|                        |         |        `${theme.config.theme_setting.author[0].desc}`        |        用户头像         |
|     `menu.enabled`     |         |       `${theme.config.theme_setting.menu[0].enabled}`        |       是否开启菜单        |
|  `menu_settings.icon`  |         |  `${theme.config.theme_setting.menu[0].menu_settings_icon}`  |      是否开启菜单图标       |
| `menu_settings.badges` |         | `${theme.config.theme_setting.menu[0].menu_settings_badges}` |    是否开启菜单badges     |
|        `scheme`        |         |            `${theme.config.theme_setting.scheme}`            |        布局方案         |
|         `site`         |         |         `${theme.config.theme_setting.site[0]} ...`          |        站点设置         |
|      `avatar.url`      |         |        `${theme.config.theme_setting.avatar[0].url}`         |         头像          |
|         侧边栏配置          |         |                            侧边栏配置                             |        侧边栏配置        |
|   `sidebar.display`    |         |         `${theme.config.sidebar.display!='remove'}`          |         侧边栏         |
|      `site_state`      |         |             `${theme.config.sidebar.site_state}`             |                     |
|        第三方插件配置         |         |                           第三方插件配置                            |       第三方插件配置       |
|     `local_search`     |         |     `${theme.config.third_plugins.local_search[0]} ...`      |       本地搜索设置        |
|    `algolia_search`    |         |    `${theme.config.third_plugins.algolia_search[0]} ...`     | algolia_search 搜索设置 |
|                        |         |                                                              |                     |
```yaml
- $formkit: repeater
name: 
label: 
help: ""
value: [{"enabled":1,"":"","":"","":"","":""}]
max: 5
min: 1
addButton: false
removeControl: false
insertControl: false
upControl: false
downControl: false
children:
- $formkit: select
  name: enabled
  id: enabled
  label: 是否启用
  value: 1
  options:
    - label: 启用
      value: 1
    - label: 关闭
      value: 0
- $formkit: text
  if: "$value.enabled === 1"
  name: 
  label: 
  help: ""
  value: ""
- $formkit: select
  if: "$value.enabled === 1"
  name: 
  label: 
  help: ""
  value: 1
  options:
    - label: 显示
      value: 1
    - label: 不显示
      value: 0
            

```