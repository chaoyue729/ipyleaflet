.. raw:: html
    :file: embed_widgets/layers_control.html

Layers Control
==============

The ``LayersControl`` allows one to display a layer selector on the map in order
to select which layers to display on the map.

Layers have a ``name`` attribute which is displayed in the selector and can be changed
by the user.

.. code::

    from ipyleaflet import (
        Map, basemaps, basemap_to_tiles,
        WMSLayer, LayersControl
    )

    m = Map(center=(50, 354), zoom=4)

    nasa_layer = basemap_to_tiles(basemaps.NASAGIBS.ModisTerraTrueColorCR, "2018-03-30")
    m.add_layer(nasa_layer)

    wms = WMSLayer(
        url="https://demo.boundlessgeo.com/geoserver/ows?",
        layers="nasa:bluemarble",
        name="nasa:bluemarble"
    )
    m.add_layer(wms)

    m.add_control(LayersControl())

    m

.. raw:: html

    <script type="application/vnd.jupyter.widget-view+json">
    {
        "model_id": "edc6adbca10a49b89effc9c6e1d0ebc7",
        "version_major": 2,
        "version_minor": 0
    }
    </script>
