#

This demonstrates the use of BaseLayerSwitcher.

```jsx
import React from 'react';
import OLMap from 'ol/Map';
import BaseLayerSwitcher from 'react-spatial/components/BaseLayerSwitcher';
import BasicMap from 'react-spatial/components/BasicMap';
import LayerService from 'react-spatial/LayerService';
import ConfigReader from 'react-spatial/ConfigReader';
import osmImage from '../../images/baselayer/osm.baselayer.png';
import osmhotImage from '../../images/baselayer/osm.baselayer.hot.png';
import openTopoImage from '../../images/baselayer/open.topo.map.png';

const center = [1149722.7037660484, 6618091.313553318];
const map = new OLMap({ controls: [] });
const layers = ConfigReader.readConfig(treeData);
const layerService = new LayerService(layers);
const layerImages = {
  osm: osmImage,
  osmhot: osmhotImage,
  opentopo: openTopoImage,
};

<div className="rs-base-layer-example">
  <BasicMap
    map={map}
    center={center}
    zoom={6}
    layers={layers}
  />
  <BaseLayerSwitcher
    layers={layers}
    layerImages={layerImages}
  />
</div>;
```
