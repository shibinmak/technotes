---
title: MapboxGL Style Spec
---

**Table of Contents**
* TOC
{:toc}


## MapboxGL Style Spec

{
  "$version": 8,
  "$root": {
    "version": {
      "required": true,
      "type": "enum",
      "values": [
        8
      ]
    },
    "name": {
      "type": "string"
    },
    "metadata": {
      "type": "*"
    },
    "center": {
      "type": "array",
      "value": "number"
    },
    "zoom": {
      "type": "number"
    },
    "bearing": {
      "type": "number",
      "default": 0,
      "period": 360,
      "units": "degrees"
    },
    "pitch": {
      "type": "number",
      "default": 0,
      "units": "degrees"
    },
    "light": {
      "type": "light"
    },
    "sources": {
      "required": true,
      "type": "sources"
    },
    "sprite": {
      "type": "string"
    },
    "glyphs": {
      "type": "string"
    },
    "transition": {
      "type": "transition"
    },
    "layers": {
      "required": true,
      "type": "array",
      "value": "layer"
    }
  },
  "sources": {
    "*": {
      "type": "source"
    }
  },
  "source": [
    "source_vector",
    "source_raster",
    "source_raster_dem",
    "source_geojson",
    "source_video",
    "source_image",
    "source_canvas"
  ],
  "source_vector": {
    "type": {
      "required": true,
      "type": "enum",
      "values": {
        "vector": {}
      }
    },
    "url": {
      "type": "string"
    },
    "tiles": {
      "type": "array",
      "value": "string"
    },
    "bounds": {
      "type": "array",
      "value": "number",
      "length": 4,
      "default": [
        -180,
        -85.0511,
        180,
        85.0511
      ]
    },
    "minzoom": {
      "type": "number",
      "default": 0
    },
    "maxzoom": {
      "type": "number",
      "default": 22
    },
    "attribution": {
      "type": "string"
    },
    "*": {
      "type": "*"
    }
  },
  "source_raster": {
    "type": {
      "required": true,
      "type": "enum",
      "values": {
        "raster": {}
      }
    },
    "url": {
      "type": "string"
    },
    "tiles": {
      "type": "array",
      "value": "string"
    },
    "bounds": {
      "type": "array",
      "value": "number",
      "length": 4,
      "default": [
        -180,
        -85.0511,
        180,
        85.0511
      ]
    },
    "minzoom": {
      "type": "number",
      "default": 0
    },
    "maxzoom": {
      "type": "number",
      "default": 22
    },
    "tileSize": {
      "type": "number",
      "default": 512,
      "units": "pixels"
    },
    "scheme": {
      "type": "enum",
      "values": {
        "xyz": {},
        "tms": {}
      },
      "default": "xyz"
    },
    "attribution": {
      "type": "string"
    },
    "*": {
      "type": "*"
    }
  },
  "source_raster_dem": {
    "type": {
      "required": true,
      "type": "enum",
      "values": {
        "raster-dem": {}
      }
    },
    "url": {
      "type": "string"
    },
    "tiles": {
      "type": "array",
      "value": "string"
    },
    "bounds": {
      "type": "array",
      "value": "number",
      "length": 4,
      "default": [
        -180,
        -85.0511,
        180,
        85.0511
      ]
    },
    "minzoom": {
      "type": "number",
      "default": 0
    },
    "maxzoom": {
      "type": "number",
      "default": 22
    },
    "tileSize": {
      "type": "number",
      "default": 512,
      "units": "pixels"
    },
    "attribution": {
      "type": "string"
    },
    "*": {
      "type": "*"
    }
  },
  "source_geojson": {
    "type": {
      "required": true,
      "type": "enum",
      "values": {
        "geojson": {}
      }
    },
    "data": {
      "type": "*"
    },
    "maxzoom": {
      "type": "number",
      "default": 18
    },
    "buffer": {
      "type": "number",
      "default": 128,
      "maximum": 512,
      "minimum": 0
    },
    "tolerance": {
      "type": "number",
      "default": 0.375
    },
    "cluster": {
      "type": "boolean",
      "default": false
    },
    "clusterRadius": {
      "type": "number",
      "default": 50,
      "minimum": 0
    },
    "clusterMaxZoom": {
      "type": "number"
    }
  },
  "source_video": {
    "type": {
      "required": true,
      "type": "enum",
      "values": {
        "video": {}
      }
    },
    "urls": {
      "required": true,
      "type": "array",
      "value": "string"
    },
    "coordinates": {
      "required": true,
      "type": "array",
      "length": 4,
      "value": {
        "type": "array",
        "length": 2,
        "value": "number"
      }
    }
  },
  "source_image": {
    "type": {
      "required": true,
      "type": "enum",
      "values": {
        "image": {}
      }
    },
    "url": {
      "required": true,
      "type": "string"
    },
    "coordinates": {
      "required": true,
      "type": "array",
      "length": 4,
      "value": {
        "type": "array",
        "length": 2,
        "value": "number"
      }
    }
  },
  "source_canvas": {
    "type": {
      "required": true,
      "type": "enum",
      "values": {
        "canvas": {}
      }
    },
    "coordinates": {
      "required": true,
      "type": "array",
      "length": 4,
      "value": {
        "type": "array",
        "length": 2,
        "value": "number"
      }
    },
    "animate": {
      "type": "boolean",
      "default": "true"
    },
    "canvas": {
      "type": "string",
      "required": true
    }
  },
  "layer": {
    "id": {
      "type": "string",
      "required": true
    },
    "type": {
      "type": "enum",
      "values": {
        "fill": {},
        "line": {},
        "symbol": {},
        "circle": {},
        "heatmap": {},
        "fill-extrusion": {},
        "raster": {},
        "hillshade": {},
        "background": {}
      },
      "required": true
    },
    "metadata": {
      "type": "*"
    },
    "source": {
      "type": "string"
    },
    "source-layer": {
      "type": "string"
    },
    "minzoom": {
      "type": "number",
      "minimum": 0,
      "maximum": 24
    },
    "maxzoom": {
      "type": "number",
      "minimum": 0,
      "maximum": 24
    },
    "filter": {
      "type": "filter"
    },
    "layout": {
      "type": "layout"
    },
    "paint": {
      "type": "paint"
    }
  },
  "layout": [
    "layout_fill",
    "layout_line",
    "layout_circle",
    "layout_heatmap",
    "layout_fill-extrusion",
    "layout_symbol",
    "layout_raster",
    "layout_hillshade",
    "layout_background"
  ],
  "layout_background": {
    "visibility": {
      "type": "enum",
      "values": {
        "visible": {},
        "none": {}
      },
      "default": "visible"
    }
  },
  "layout_fill": {
    "visibility": {
      "type": "enum",
      "values": {
        "visible": {},
        "none": {}
      },
      "default": "visible"
    }
  },
  "layout_circle": {
    "visibility": {
      "type": "enum",
      "values": {
        "visible": {},
        "none": {}
      },
      "default": "visible"
    }
  },
  "layout_heatmap": {
    "visibility": {
      "type": "enum",
      "values": {
        "visible": {},
        "none": {}
      },
      "default": "visible"
    }
  },
  "layout_fill-extrusion": {
    "visibility": {
      "type": "enum",
      "values": {
        "visible": {},
        "none": {}
      },
      "default": "visible"
    }
  },
  "layout_line": {
    "line-cap": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "butt": {},
        "round": {},
        "square": {}
      },
      "default": "butt"
    },
    "line-join": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "property-function": true,
      "values": {
        "bevel": {},
        "round": {},
        "miter": {}
      },
      "default": "miter"
    },
    "line-miter-limit": {
      "type": "number",
      "default": 2,
      "function": "interpolated",
      "zoom-function": true,
      "requires": [
        {
          "line-join": "miter"
        }
      ]
    },
    "line-round-limit": {
      "type": "number",
      "default": 1.05,
      "function": "interpolated",
      "zoom-function": true,
      "requires": [
        {
          "line-join": "round"
        }
      ]
    },
    "visibility": {
      "type": "enum",
      "values": {
        "visible": {},
        "none": {}
      },
      "default": "visible"
    }
  },
  "layout_symbol": {
    "symbol-placement": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "point": {},
        "line": {}
      },
      "default": "point"
    },
    "symbol-spacing": {
      "type": "number",
      "default": 250,
      "minimum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "units": "pixels",
      "requires": [
        {
          "symbol-placement": "line"
        }
      ]
    },
    "symbol-avoid-edges": {
      "type": "boolean",
      "function": "piecewise-constant",
      "zoom-function": true,
      "default": false
    },
    "icon-allow-overlap": {
      "type": "boolean",
      "function": "piecewise-constant",
      "zoom-function": true,
      "default": false,
      "requires": [
        "icon-image"
      ]
    },
    "icon-ignore-placement": {
      "type": "boolean",
      "function": "piecewise-constant",
      "zoom-function": true,
      "default": false,
      "requires": [
        "icon-image"
      ]
    },
    "icon-optional": {
      "type": "boolean",
      "function": "piecewise-constant",
      "zoom-function": true,
      "default": false,
      "requires": [
        "icon-image",
        "text-field"
      ]
    },
    "icon-rotation-alignment": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {},
        "auto": {}
      },
      "default": "auto",
      "requires": [
        "icon-image"
      ]
    },
    "icon-size": {
      "type": "number",
      "default": 1,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "units": "factor of the original icon size",
      "requires": [
        "icon-image"
      ]
    },
    "icon-text-fit": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "none": {},
        "width": {},
        "height": {},
        "both": {}
      },
      "default": "none",
      "requires": [
        "icon-image",
        "text-field"
      ]
    },
    "icon-text-fit-padding": {
      "type": "array",
      "value": "number",
      "length": 4,
      "default": [
        0,
        0,
        0,
        0
      ],
      "units": "pixels",
      "function": "interpolated",
      "zoom-function": true,
      "requires": [
        "icon-image",
        "text-field",
        {
          "icon-text-fit": [
            "both",
            "width",
            "height"
          ]
        }
      ]
    },
    "icon-image": {
      "type": "string",
      "function": "piecewise-constant",
      "zoom-function": true,
      "property-function": true,
      "tokens": true
    },
    "icon-rotate": {
      "type": "number",
      "default": 0,
      "period": 360,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "units": "degrees",
      "requires": [
        "icon-image"
      ]
    },
    "icon-padding": {
      "type": "number",
      "default": 2,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "units": "pixels",
      "requires": [
        "icon-image"
      ]
    },
    "icon-keep-upright": {
      "type": "boolean",
      "function": "piecewise-constant",
      "zoom-function": true,
      "default": false,
      "requires": [
        "icon-image",
        {
          "icon-rotation-alignment": "map"
        },
        {
          "symbol-placement": "line"
        }
      ]
    },
    "icon-offset": {
      "type": "array",
      "value": "number",
      "length": 2,
      "default": [
        0,
        0
      ],
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "requires": [
        "icon-image"
      ]
    },
    "icon-anchor": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "property-function": true,
      "values": {
        "center": {},
        "left": {},
        "right": {},
        "top": {},
        "bottom": {},
        "top-left": {},
        "top-right": {},
        "bottom-left": {},
        "bottom-right": {}
      },
      "default": "center",
      "requires": [
        "icon-image"
      ]
    },
    "icon-pitch-alignment": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {},
        "auto": {}
      },
      "default": "auto",
      "requires": [
        "icon-image"
      ]
    },
    "text-pitch-alignment": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {},
        "auto": {}
      },
      "default": "auto",
      "requires": [
        "text-field"
      ]
    },
    "text-rotation-alignment": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {},
        "auto": {}
      },
      "default": "auto",
      "requires": [
        "text-field"
      ]
    },
    "text-field": {
      "type": "string",
      "function": "piecewise-constant",
      "zoom-function": true,
      "property-function": true,
      "default": "",
      "tokens": true
    },
    "text-font": {
      "type": "array",
      "value": "string",
      "function": "piecewise-constant",
      "zoom-function": true,
      "property-function": true,
      "default": [
        "Open Sans Regular",
        "Arial Unicode MS Regular"
      ],
      "requires": [
        "text-field"
      ]
    },
    "text-size": {
      "type": "number",
      "default": 16,
      "minimum": 0,
      "units": "pixels",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "requires": [
        "text-field"
      ]
    },
    "text-max-width": {
      "type": "number",
      "default": 10,
      "minimum": 0,
      "units": "ems",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "requires": [
        "text-field"
      ]
    },
    "text-line-height": {
      "type": "number",
      "default": 1.2,
      "units": "ems",
      "function": "interpolated",
      "zoom-function": true,
      "requires": [
        "text-field"
      ]
    },
    "text-letter-spacing": {
      "type": "number",
      "default": 0,
      "units": "ems",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "requires": [
        "text-field"
      ]
    },
    "text-justify": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "property-function": true,
      "values": {
        "left": {},
        "center": {},
        "right": {}
      },
      "default": "center",
      "requires": [
        "text-field"
      ]
    },
    "text-anchor": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "property-function": true,
      "values": {
        "center": {},
        "left": {},
        "right": {},
        "top": {},
        "bottom": {},
        "top-left": {},
        "top-right": {},
        "bottom-left": {},
        "bottom-right": {}
      },
      "default": "center",
      "requires": [
        "text-field"
      ]
    },
    "text-max-angle": {
      "type": "number",
      "default": 45,
      "units": "degrees",
      "function": "interpolated",
      "zoom-function": true,
      "requires": [
        "text-field",
        {
          "symbol-placement": "line"
        }
      ]
    },
    "text-rotate": {
      "type": "number",
      "default": 0,
      "period": 360,
      "units": "degrees",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "requires": [
        "text-field"
      ]
    },
    "text-padding": {
      "type": "number",
      "default": 2,
      "minimum": 0,
      "units": "pixels",
      "function": "interpolated",
      "zoom-function": true,
      "requires": [
        "text-field"
      ]
    },
    "text-keep-upright": {
      "type": "boolean",
      "function": "piecewise-constant",
      "zoom-function": true,
      "default": true,
      "requires": [
        "text-field",
        {
          "text-rotation-alignment": "map"
        },
        {
          "symbol-placement": "line"
        }
      ]
    },
    "text-transform": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "property-function": true,
      "values": {
        "none": {},
        "uppercase": {},
        "lowercase": {}
      },
      "default": "none",
      "requires": [
        "text-field"
      ]
    },
    "text-offset": {
      "type": "array",
      "value": "number",
      "units": "ems",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "length": 2,
      "default": [
        0,
        0
      ],
      "requires": [
        "text-field"
      ]
    },
    "text-allow-overlap": {
      "type": "boolean",
      "function": "piecewise-constant",
      "zoom-function": true,
      "default": false,
      "requires": [
        "text-field"
      ]
    },
    "text-ignore-placement": {
      "type": "boolean",
      "function": "piecewise-constant",
      "zoom-function": true,
      "default": false,
      "requires": [
        "text-field"
      ]
    },
    "text-optional": {
      "type": "boolean",
      "function": "piecewise-constant",
      "zoom-function": true,
      "default": false,
      "requires": [
        "text-field",
        "icon-image"
      ]
    },
    "visibility": {
      "type": "enum",
      "values": {
        "visible": {},
        "none": {}
      },
      "default": "visible"
    }
  },
  "layout_raster": {
    "visibility": {
      "type": "enum",
      "values": {
        "visible": {},
        "none": {}
      },
      "default": "visible"
    }
  },
  "layout_hillshade": {
    "visibility": {
      "type": "enum",
      "values": {
        "visible": {},
        "none": {}
      },
      "default": "visible"
    }
  },
  "filter": {
    "type": "array",
    "value": "*"
  },
  "filter_operator": {
    "type": "enum",
    "values": {
      "==": {},
      "!=": {},
      ">": {},
      ">=": {},
      "<": {},
      "<=": {},
      "in": {},
      "!in": {},
      "all": {},
      "any": {},
      "none": {},
      "has": {},
      "!has": {}
    }
  },
  "geometry_type": {
    "type": "enum",
    "values": {
      "Point": {},
      "LineString": {},
      "Polygon": {}
    }
  },
  "function": {
    "expression": {
      "type": "expression"
    },
    "stops": {
      "type": "array",
      "value": "function_stop"
    },
    "base": {
      "type": "number",
      "default": 1,
      "minimum": 0
    },
    "property": {
      "type": "string",
      "default": "$zoom"
    },
    "type": {
      "type": "enum",
      "values": {
        "identity": {},
        "exponential": {},
        "interval": {},
        "categorical": {}
      },
      "default": "exponential"
    },
    "colorSpace": {
      "type": "enum",
      "values": {
        "rgb": {},
        "lab": {},
        "hcl": {}
      },
      "default": "rgb"
    },
    "default": {
      "type": "*",
      "required": false
    }
  },
  "function_stop": {
    "type": "array",
    "minimum": 0,
    "maximum": 22,
    "value": [
      "number",
      "color"
    ],
    "length": 2
  },
  "expression": {
    "type": "array",
    "value": "*",
    "minimum": 1
  },
  "expression_name": {
    "type": "enum",
    "values": {
      "let": {
        "group": "Variable binding"
      },
      "var": {
        "group": "Variable binding"
      },
      "literal": {
        "group": "Types"
      },
      "array": {
        "group": "Types"
      },
      "at": {
        "group": "Lookup"
      },
      "case": {
        "group": "Decision"
      },
      "match": {
        "group": "Decision"
      },
      "coalesce": {
        "group": "Decision"
      },
      "step": {
        "group": "Ramps, scales, curves"
      },
      "interpolate": {
        "group": "Ramps, scales, curves"
      },
      "ln2": {
        "group": "Math"
      },
      "pi": {
        "group": "Math"
      },
      "e": {
        "group": "Math"
      },
      "typeof": {
        "group": "Types"
      },
      "string": {
        "group": "Types"
      },
      "number": {
        "group": "Types"
      },
      "boolean": {
        "group": "Types"
      },
      "object": {
        "group": "Types"
      },
      "to-string": {
        "group": "Types"
      },
      "to-number": {
        "group": "Types"
      },
      "to-boolean": {
        "group": "Types"
      },
      "to-rgba": {
        "group": "Color"
      },
      "to-color": {
        "group": "Types"
      },
      "rgb": {
        "group": "Color"
      },
      "rgba": {
        "group": "Color"
      },
      "get": {
        "group": "Lookup"
      },
      "has": {
        "group": "Lookup"
      },
      "length": {
        "group": "Lookup"
      },
      "properties": {
        "group": "Feature data"
      },
      "geometry-type": {
        "group": "Feature data"
      },
      "id": {
        "group": "Feature data"
      },
      "zoom": {
        "group": "Zoom"
      },
      "heatmap-density": {
        "group": "Heatmap"
      },
      "+": {
        "group": "Math"
      },
      "*": {
        "group": "Math"
      },
      "-": {
        "group": "Math"
      },
      "/": {
        "group": "Math"
      },
      "%": {
        "group": "Math"
      },
      "^": {
        "group": "Math"
      },
      "sqrt": {
        "group": "Math"
      },
      "log10": {
        "group": "Math"
      },
      "ln": {
        "group": "Math"
      },
      "log2": {
        "group": "Math"
      },
      "sin": {
        "group": "Math"
      },
      "cos": {
        "group": "Math"
      },
      "tan": {
        "group": "Math"
      },
      "asin": {
        "group": "Math"
      },
      "acos": {
        "group": "Math"
      },
      "atan": {
        "group": "Math"
      },
      "min": {
        "group": "Math"
      },
      "max": {
        "group": "Math"
      },
      "==": {
        "group": "Decision"
      },
      "!=": {
        "group": "Decision"
      },
      ">": {
        "group": "Decision"
      },
      "<": {
        "group": "Decision"
      },
      ">=": {
        "group": "Decision"
      },
      "<=": {
        "group": "Decision"
      },
      "all": {
        "group": "Decision"
      },
      "any": {
        "group": "Decision"
      },
      "!": {
        "group": "Decision"
      },
      "upcase": {
        "group": "String"
      },
      "downcase": {
        "group": "String"
      },
      "concat": {
        "group": "String"
      }
    }
  },
  "light": {
    "anchor": {
      "type": "enum",
      "default": "viewport",
      "values": {
        "map": {},
        "viewport": {}
      },
      "transition": false,
      "zoom-function": true,
      "property-function": false,
      "function": "piecewise-constant"
    },
    "position": {
      "type": "array",
      "default": [
        1.15,
        210,
        30
      ],
      "length": 3,
      "value": "number",
      "transition": true,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": false
    },
    "color": {
      "type": "color",
      "default": "#ffffff",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": false,
      "transition": true
    },
    "intensity": {
      "type": "number",
      "default": 0.5,
      "minimum": 0,
      "maximum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": false,
      "transition": true
    }
  },
  "paint": [
    "paint_fill",
    "paint_line",
    "paint_circle",
    "paint_heatmap",
    "paint_fill-extrusion",
    "paint_symbol",
    "paint_raster",
    "paint_hillshade",
    "paint_background"
  ],
  "paint_fill": {
    "fill-antialias": {
      "type": "boolean",
      "function": "piecewise-constant",
      "zoom-function": true,
      "default": true
    },
    "fill-opacity": {
      "type": "number",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "default": 1,
      "minimum": 0,
      "maximum": 1,
      "transition": true
    },
    "fill-color": {
      "type": "color",
      "default": "#000000",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "requires": [
        {
          "!": "fill-pattern"
        }
      ]
    },
    "fill-outline-color": {
      "type": "color",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "requires": [
        {
          "!": "fill-pattern"
        },
        {
          "fill-antialias": true
        }
      ]
    },
    "fill-translate": {
      "type": "array",
      "value": "number",
      "length": 2,
      "default": [
        0,
        0
      ],
      "function": "interpolated",
      "zoom-function": true,
      "transition": true,
      "units": "pixels"
    },
    "fill-translate-anchor": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {}
      },
      "default": "map",
      "requires": [
        "fill-translate"
      ]
    },
    "fill-pattern": {
      "type": "string",
      "function": "piecewise-constant",
      "zoom-function": true,
      "transition": true
    }
  },
  "paint_fill-extrusion": {
    "fill-extrusion-opacity": {
      "type": "number",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": false,
      "default": 1,
      "minimum": 0,
      "maximum": 1,
      "transition": true
    },
    "fill-extrusion-color": {
      "type": "color",
      "default": "#000000",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "requires": [
        {
          "!": "fill-extrusion-pattern"
        }
      ]
    },
    "fill-extrusion-translate": {
      "type": "array",
      "value": "number",
      "length": 2,
      "default": [
        0,
        0
      ],
      "function": "interpolated",
      "zoom-function": true,
      "transition": true,
      "units": "pixels"
    },
    "fill-extrusion-translate-anchor": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {}
      },
      "default": "map",
      "requires": [
        "fill-extrusion-translate"
      ]
    },
    "fill-extrusion-pattern": {
      "type": "string",
      "function": "piecewise-constant",
      "zoom-function": true,
      "transition": true
    },
    "fill-extrusion-height": {
      "type": "number",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "default": 0,
      "minimum": 0,
      "units": "meters",
      "transition": true
    },
    "fill-extrusion-base": {
      "type": "number",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "default": 0,
      "minimum": 0,
      "units": "meters",
      "transition": true,
      "requires": [
        "fill-extrusion-height"
      ]
    }
  },
  "paint_line": {
    "line-opacity": {
      "type": "number",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "default": 1,
      "minimum": 0,
      "maximum": 1,
      "transition": true
    },
    "line-color": {
      "type": "color",
      "default": "#000000",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "requires": [
        {
          "!": "line-pattern"
        }
      ]
    },
    "line-translate": {
      "type": "array",
      "value": "number",
      "length": 2,
      "default": [
        0,
        0
      ],
      "function": "interpolated",
      "zoom-function": true,
      "transition": true,
      "units": "pixels"
    },
    "line-translate-anchor": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {}
      },
      "default": "map",
      "requires": [
        "line-translate"
      ]
    },
    "line-width": {
      "type": "number",
      "default": 1,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "units": "pixels"
    },
    "line-gap-width": {
      "type": "number",
      "default": 0,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "units": "pixels"
    },
    "line-offset": {
      "type": "number",
      "default": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "units": "pixels"
    },
    "line-blur": {
      "type": "number",
      "default": 0,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "units": "pixels"
    },
    "line-dasharray": {
      "type": "array",
      "value": "number",
      "function": "piecewise-constant",
      "zoom-function": true,
      "minimum": 0,
      "transition": true,
      "units": "line widths",
      "requires": [
        {
          "!": "line-pattern"
        }
      ]
    },
    "line-pattern": {
      "type": "string",
      "function": "piecewise-constant",
      "zoom-function": true,
      "transition": true
    }
  },
  "paint_circle": {
    "circle-radius": {
      "type": "number",
      "default": 5,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "units": "pixels"
    },
    "circle-color": {
      "type": "color",
      "default": "#000000",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true
    },
    "circle-blur": {
      "type": "number",
      "default": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true
    },
    "circle-opacity": {
      "type": "number",
      "default": 1,
      "minimum": 0,
      "maximum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true
    },
    "circle-translate": {
      "type": "array",
      "value": "number",
      "length": 2,
      "default": [
        0,
        0
      ],
      "function": "interpolated",
      "zoom-function": true,
      "transition": true,
      "units": "pixels"
    },
    "circle-translate-anchor": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {}
      },
      "default": "map",
      "requires": [
        "circle-translate"
      ]
    },
    "circle-pitch-scale": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {}
      },
      "default": "map"
    },
    "circle-pitch-alignment": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {}
      },
      "default": "viewport"
    },
    "circle-stroke-width": {
      "type": "number",
      "default": 0,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "units": "pixels"
    },
    "circle-stroke-color": {
      "type": "color",
      "default": "#000000",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true
    },
    "circle-stroke-opacity": {
      "type": "number",
      "default": 1,
      "minimum": 0,
      "maximum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true
    }
  },
  "paint_heatmap": {
    "heatmap-radius": {
      "type": "number",
      "default": 30,
      "minimum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "units": "pixels"
    },
    "heatmap-weight": {
      "type": "number",
      "default": 1,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": false
    },
    "heatmap-intensity": {
      "type": "number",
      "default": 1,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": false,
      "transition": true
    },
    "heatmap-color": {
      "type": "color",
      "default": [
        "interpolate",
        [
          "linear"
        ],
        [
          "heatmap-density"
        ],
        0,
        "rgba(0, 0, 255, 0)",
        0.1,
        "royalblue",
        0.3,
        "cyan",
        0.5,
        "lime",
        0.7,
        "yellow",
        1,
        "red"
      ],
      "function": "interpolated",
      "zoom-function": false,
      "property-function": false,
      "transition": false
    },
    "heatmap-opacity": {
      "type": "number",
      "default": 1,
      "minimum": 0,
      "maximum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": false,
      "transition": true
    }
  },
  "paint_symbol": {
    "icon-opacity": {
      "type": "number",
      "default": 1,
      "minimum": 0,
      "maximum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "requires": [
        "icon-image"
      ]
    },
    "icon-color": {
      "type": "color",
      "default": "#000000",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "requires": [
        "icon-image"
      ]
    },
    "icon-halo-color": {
      "type": "color",
      "default": "rgba(0, 0, 0, 0)",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "requires": [
        "icon-image"
      ]
    },
    "icon-halo-width": {
      "type": "number",
      "default": 0,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "units": "pixels",
      "requires": [
        "icon-image"
      ]
    },
    "icon-halo-blur": {
      "type": "number",
      "default": 0,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "units": "pixels",
      "requires": [
        "icon-image"
      ]
    },
    "icon-translate": {
      "type": "array",
      "value": "number",
      "length": 2,
      "default": [
        0,
        0
      ],
      "function": "interpolated",
      "zoom-function": true,
      "transition": true,
      "units": "pixels",
      "requires": [
        "icon-image"
      ]
    },
    "icon-translate-anchor": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {}
      },
      "default": "map",
      "requires": [
        "icon-image",
        "icon-translate"
      ]
    },
    "text-opacity": {
      "type": "number",
      "default": 1,
      "minimum": 0,
      "maximum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "requires": [
        "text-field"
      ]
    },
    "text-color": {
      "type": "color",
      "default": "#000000",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "requires": [
        "text-field"
      ]
    },
    "text-halo-color": {
      "type": "color",
      "default": "rgba(0, 0, 0, 0)",
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "requires": [
        "text-field"
      ]
    },
    "text-halo-width": {
      "type": "number",
      "default": 0,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "units": "pixels",
      "requires": [
        "text-field"
      ]
    },
    "text-halo-blur": {
      "type": "number",
      "default": 0,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "property-function": true,
      "transition": true,
      "units": "pixels",
      "requires": [
        "text-field"
      ]
    },
    "text-translate": {
      "type": "array",
      "value": "number",
      "length": 2,
      "default": [
        0,
        0
      ],
      "function": "interpolated",
      "zoom-function": true,
      "transition": true,
      "units": "pixels",
      "requires": [
        "text-field"
      ]
    },
    "text-translate-anchor": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {}
      },
      "default": "map",
      "requires": [
        "text-field",
        "text-translate"
      ]
    }
  },
  "paint_raster": {
    "raster-opacity": {
      "type": "number",
      "default": 1,
      "minimum": 0,
      "maximum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "transition": true
    },
    "raster-hue-rotate": {
      "type": "number",
      "default": 0,
      "period": 360,
      "function": "interpolated",
      "zoom-function": true,
      "transition": true,
      "units": "degrees"
    },
    "raster-brightness-min": {
      "type": "number",
      "function": "interpolated",
      "zoom-function": true,
      "default": 0,
      "minimum": 0,
      "maximum": 1,
      "transition": true
    },
    "raster-brightness-max": {
      "type": "number",
      "function": "interpolated",
      "zoom-function": true,
      "default": 1,
      "minimum": 0,
      "maximum": 1,
      "transition": true
    },
    "raster-saturation": {
      "type": "number",
      "default": 0,
      "minimum": -1,
      "maximum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "transition": true
    },
    "raster-contrast": {
      "type": "number",
      "default": 0,
      "minimum": -1,
      "maximum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "transition": true
    },
    "raster-fade-duration": {
      "type": "number",
      "default": 300,
      "minimum": 0,
      "function": "interpolated",
      "zoom-function": true,
      "transition": false,
      "units": "milliseconds"
    }
  },
  "paint_hillshade": {
    "hillshade-illumination-direction": {
      "type": "number",
      "default": 335,
      "minimum": 0,
      "maximum": 359,
      "function": "interpolated",
      "zoom-function": true,
      "transition": false
    },
    "hillshade-illumination-anchor": {
      "type": "enum",
      "function": "piecewise-constant",
      "zoom-function": true,
      "values": {
        "map": {},
        "viewport": {}
      },
      "default": "viewport"
    },
    "hillshade-exaggeration": {
      "type": "number",
      "default": 0.5,
      "minimum": 0,
      "maximum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "transition": true
    },
    "hillshade-shadow-color": {
      "type": "color",
      "default": "#000000",
      "function": "interpolated",
      "zoom-function": true,
      "transition": true
    },
    "hillshade-highlight-color": {
      "type": "color",
      "default": "#FFFFFF",
      "function": "interpolated",
      "zoom-function": true,
      "transition": true
    },
    "hillshade-accent-color": {
      "type": "color",
      "default": "#000000",
      "function": "interpolated",
      "zoom-function": true,
      "transition": true
    }
  },
  "paint_background": {
    "background-color": {
      "type": "color",
      "default": "#000000",
      "function": "interpolated",
      "zoom-function": true,
      "transition": true,
      "requires": [
        {
          "!": "background-pattern"
        }
      ]
    },
    "background-pattern": {
      "type": "string",
      "function": "piecewise-constant",
      "zoom-function": true,
      "transition": true
    },
    "background-opacity": {
      "type": "number",
      "default": 1,
      "minimum": 0,
      "maximum": 1,
      "function": "interpolated",
      "zoom-function": true,
      "transition": true
    }
  },
  "transition": {
    "duration": {
      "type": "number",
      "default": 300,
      "minimum": 0,
      "units": "milliseconds"
    },
    "delay": {
      "type": "number",
      "default": 0,
      "minimum": 0,
      "units": "milliseconds"
    }
  }
}