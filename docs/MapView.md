## <MapboxGL.MapView />
### MapView backed by Mapbox Native GL

### props
| Prop | Type | Default | Required | Description |
| ---- | :--: | :-----: | :------: | :----------: |
| contentInset | `union` | `none` | `false` | The distance from the edges of the map view’s frame to the edges of the map view’s logical viewport. |
| style | `any` | `none` | `false` | Style for wrapping React Native View |
| styleURL | `string` | `MapboxGL.StyleURL.Street` | `false` | Style URL for map |
| preferredFramesPerSecond | `number` | `none` | `false` | iOS: The preferred frame rate at which the map view is rendered.<br/>The default value for this property is MGLMapViewPreferredFramesPerSecondDefault,<br/>which will adaptively set the preferred frame rate based on the capability of<br/>the user’s device to maintain a smooth experience. This property can be set to arbitrary integer values.<br/><br/>Android: The maximum frame rate at which the map view is rendered, but it can't excess the ability of device hardware.<br/>This property can be set to arbitrary integer values. |
| localizeLabels | `bool` | `false` | `false` | Automatically change the language of the map labels to the system’s preferred language,<br/>this is not something that can be toggled on/off |
| zoomEnabled | `bool` | `none` | `false` | Enable/Disable zoom on the map |
| scrollEnabled | `bool` | `true` | `false` | Enable/Disable scroll on the map |
| pitchEnabled | `bool` | `true` | `false` | Enable/Disable pitch on map |
| rotateEnabled | `bool` | `true` | `false` | Enable/Disable rotation on map |
| attributionEnabled | `bool` | `true` | `false` | The Mapbox terms of service, which governs the use of Mapbox-hosted vector tiles and styles,<br/>[requires](https://www.mapbox.com/help/how-attribution-works/) these copyright notices to accompany any map that features Mapbox-designed styles, OpenStreetMap data, or other Mapbox data such as satellite or terrain data.<br/>If that applies to this map view, do not hide this view or remove any notices from it.<br/><br/>You are additionally [required](https://www.mapbox.com/help/how-mobile-apps-work/#telemetry) to provide users with the option to disable anonymous usage and location sharing (telemetry).<br/>If this view is hidden, you must implement this setting elsewhere in your app. See our website for [Android](https://www.mapbox.com/android-docs/map-sdk/overview/#telemetry-opt-out) and [iOS](https://www.mapbox.com/ios-sdk/#telemetry_opt_out) for implementation details.<br/><br/>Enable/Disable attribution on map. For iOS you need to add MGLMapboxMetricsEnabledSettingShownInApp=YES<br/>to your Info.plist |
| attributionPosition | `union` | `none` | `false` | Adds attribution offset, e.g. `{top: 8, left: 8}` will put attribution button in top-left corner of the map |
| logoEnabled | `bool` | `true` | `false` | Enable/Disable the logo on the map. |
| compassEnabled | `bool` | `none` | `false` | Enable/Disable the compass from appearing on the map |
| compassViewPosition | `number` | `1` | `false` | Change corner of map the compass starts at. (iOS only) 0: TopLeft, 1: TopRight, 2: BottomLeft, 3: BottomRight |
| compassViewMargins | `object` | `none` | `false` | Add margins to the compass. |
| surfaceView | `bool` | `false` | `false` | [Android only] Enable/Disable use of GLSurfaceView insted of TextureView. |
| onPress | `func` | `none` | `false` | Map press listener, gets called when a user presses the map |
| onLongPress | `func` | `none` | `false` | Map long press listener, gets called when a user long presses the map |
| onRegionWillChange | `func` | `none` | `false` | This event is triggered whenever the currently displayed map region is about to change. |
| onRegionIsChanging | `func` | `none` | `false` | This event is triggered whenever the currently displayed map region is changing. |
| onRegionDidChange | `func` | `none` | `false` | This event is triggered whenever the currently displayed map region finished changing |
| onWillStartLoadingMap | `func` | `none` | `false` | This event is triggered when the map is about to start loading a new map style. |
| onDidFinishLoadingMap | `func` | `none` | `false` | This is triggered when the map has successfully loaded a new map style. |
| onDidFailLoadingMap | `func` | `none` | `false` | This event is triggered when the map has failed to load a new map style. |
| onWillStartRenderingFrame | `func` | `none` | `false` | This event is triggered when the map will start rendering a frame. |
| onDidFinishRenderingFrame | `func` | `none` | `false` | This event is triggered when the map finished rendering a frame. |
| onDidFinishRenderingFrameFully | `func` | `none` | `false` | This event is triggered when the map fully finished rendering a frame. |
| onWillStartRenderingMap | `func` | `none` | `false` | This event is triggered when the map will start rendering the map. |
| onDidFinishRenderingMap | `func` | `none` | `false` | This event is triggered when the map finished rendering the map. |
| onDidFinishRenderingMapFully | `func` | `none` | `false` | This event is triggered when the map fully finished rendering the map. |
| onUserLocationUpdate | `func` | `none` | `false` | This event is triggered when the user location is updated. |
| onDidFinishLoadingStyle | `func` | `none` | `false` | This event is triggered when a style has finished loading. |
| regionWillChangeDebounceTime | `number` | `10` | `false` | The emitted frequency of regionwillchange events |
| regionDidChangeDebounceTime | `number` | `500` | `false` | The emitted frequency of regiondidchange events |

### methods
#### getPointInView(coordinate)

Converts a geographic coordinate to a point in the given view’s coordinate system.

##### arguments
| Name | Type | Required | Description  |
| ---- | :--: | :------: | :----------: |
| `coordinate` | `Array` | `Yes` | A point expressed in the map view's coordinate system. |



```javascript
const pointInView = await this._map.getPointInView([-37.817070, 144.949901]);
```


#### getCoordinateFromView(point)

Converts a point in the given view’s coordinate system to a geographic coordinate.

##### arguments
| Name | Type | Required | Description  |
| ---- | :--: | :------: | :----------: |
| `point` | `Array` | `Yes` | A point expressed in the given view’s coordinate system. |



```javascript
const coordinate = await this._map.getCoordinateFromView([100, 100]);
```


#### getVisibleBounds()

The coordinate bounds(ne, sw) visible in the users’s viewport.

##### arguments
| Name | Type | Required | Description  |
| ---- | :--: | :------: | :----------: |




```javascript
const visibleBounds = await this._map.getVisibleBounds();
```


#### queryRenderedFeaturesAtPoint(coordinate[, filter][, layerIDs])

Returns an array of rendered map features that intersect with a given point.

##### arguments
| Name | Type | Required | Description  |
| ---- | :--: | :------: | :----------: |
| `coordinate` | `Array` | `Yes` | A point expressed in the map view’s coordinate system. |
| `filter` | `Array` | `No` | A set of strings that correspond to the names of layers defined in the current style. Only the features contained in these layers are included in the returned array. |
| `layerIDs` | `Array` | `No` | A array of layer id's to filter the features by |



```javascript
this._map.queryRenderedFeaturesAtPoint([30, 40], ['==', 'type', 'Point'], ['id1', 'id2'])
```


#### queryRenderedFeaturesInRect(bbox[, filter][, layerIDs])

Returns an array of rendered map features that intersect with the given rectangle,<br/>restricted to the given style layers and filtered by the given predicate.

##### arguments
| Name | Type | Required | Description  |
| ---- | :--: | :------: | :----------: |
| `bbox` | `Array` | `Yes` | A rectangle expressed in the map view’s coordinate system. |
| `filter` | `Array` | `No` | A set of strings that correspond to the names of layers defined in the current style. Only the features contained in these layers are included in the returned array. |
| `layerIDs` | `Array` | `No` |  A array of layer id's to filter the features by |



```javascript
this._map.queryRenderedFeaturesInRect([30, 40, 20, 10], ['==', 'type', 'Point'], ['id1', 'id2'])
```


#### setCamera()

Map camera will perform updates based on provided config. Deprecated use Camera#setCamera.

##### arguments
| Name | Type | Required | Description  |
| ---- | :--: | :------: | :----------: |



#### takeSnap(writeToDisk)

Takes snapshot of map with current tiles and returns a URI to the image

##### arguments
| Name | Type | Required | Description  |
| ---- | :--: | :------: | :----------: |
| `writeToDisk` | `Boolean` | `Yes` | If true will create a temp file, otherwise it is in base64 |


#### getZoom()

Returns the current zoom of the map view.

##### arguments
| Name | Type | Required | Description  |
| ---- | :--: | :------: | :----------: |




```javascript
const zoom = await this._map.getZoom();
```


#### getCenter()

Returns the map's geographical centerpoint

##### arguments
| Name | Type | Required | Description  |
| ---- | :--: | :------: | :----------: |




```javascript
const center = await this._map.getCenter();
```


#### showAttribution()

Show the attribution and telemetry action sheet.<br/>If you implement a custom attribution button, you should add this action to the button.

##### arguments
| Name | Type | Required | Description  |
| ---- | :--: | :------: | :----------: |




