{
  "datasource": {
    "type": "prometheus",
    "uid": "djoI8bg4k"
  },
  "fieldConfig": {
    "defaults": {
      "custom": {
        "align": "center",
        "cellOptions": {
          "type": "auto"
        },
        "inspect": false
      },
      "mappings": [],
      "thresholds": {
        "mode": "absolute",
        "steps": [
          {
            "color": "semi-dark-green",
            "value": null
          },
          {
            "color": "semi-dark-yellow",
            "value": 75
          },
          {
            "color": "semi-dark-red",
            "value": 80
          }
        ]
      },
      "color": {
        "mode": "thresholds"
      },
      "max": 100
    },
    "overrides": [
      {
        "matcher": {
          "id": "byName",
          "options": "CPU Load"
        },
        "properties": [
          {
            "id": "custom.cellOptions",
            "value": {
              "mode": "lcd",
              "type": "gauge"
            }
          },
          {
            "id": "thresholds",
            "value": {
              "mode": "absolute",
              "steps": [
                {
                  "color": "green",
                  "value": null
                },
                {
                  "color": "#EAB839",
                  "value": 75
                },
                {
                  "color": "red",
                  "value": 95
                }
              ]
            }
          },
          {
            "id": "custom.width",
            "value": 231
          }
        ]
      },
      {
        "matcher": {
          "id": "byName",
          "options": "RAM"
        },
        "properties": [
          {
            "id": "custom.cellOptions",
            "value": {
              "mode": "basic",
              "type": "gauge"
            }
          },
          {
            "id": "thresholds",
            "value": {
              "mode": "absolute",
              "steps": [
                {
                  "color": "green",
                  "value": null
                },
                {
                  "color": "#EAB839",
                  "value": 75
                },
                {
                  "color": "red",
                  "value": 95
                }
              ]
            }
          }
        ]
      },
      {
        "matcher": {
          "id": "byName",
          "options": "Disk Usage"
        },
        "properties": [
          {
            "id": "custom.cellOptions",
            "value": {
              "mode": "lcd",
              "type": "gauge"
            }
          },
          {
            "id": "thresholds",
            "value": {
              "mode": "absolute",
              "steps": [
                {
                  "color": "green",
                  "value": null
                },
                {
                  "color": "#EAB839",
                  "value": 80
                },
                {
                  "color": "red",
                  "value": 95
                }
              ]
            }
          }
        ]
      },
      {
        "matcher": {
          "id": "byName",
          "options": "Node"
        },
        "properties": [
          {
            "id": "mappings",
            "value": [
              {
                "options": {
                  "pattern": "(.*):9796",
                  "result": {
                    "index": 0,
                    "text": "$1"
                  }
                },
                "type": "regex"
              }
            ]
          },
          {
            "id": "custom.width",
            "value": 140
          }
        ]
      },
      {
        "matcher": {
          "id": "byName",
          "options": "Cores"
        },
        "properties": [
          {
            "id": "custom.cellOptions",
            "value": {
              "mode": "basic",
              "type": "color-background"
            }
          },
          {
            "id": "color",
            "value": {
              "fixedColor": "semi-dark-blue",
              "mode": "fixed"
            }
          },
          {
            "id": "custom.width",
            "value": 86
          }
        ]
      }
    ]
  },
  "gridPos": {
    "h": 15,
    "w": 19,
    "x": 5,
    "y": 9
  },
  "id": 12,
  "options": {
    "showHeader": true,
    "cellHeight": "sm",
    "footer": {
      "show": false,
      "reducer": [
        "sum"
      ],
      "countRows": false,
      "fields": ""
    },
    "frameIndex": 0,
    "sortBy": [
      {
        "desc": true,
        "displayName": "RAM"
      }
    ]
  },
  "pluginVersion": "9.5.2",
  "targets": [
    {
      "datasource": {
        "type": "prometheus",
        "uid": "djoI8bg4k"
      },
      "editorMode": "code",
      "expr": "(sum by (instance) (node_cpu_seconds_total{job=\"linux_vm\",mode!=\"idle\"})) / (sum by (instance) (node_cpu_seconds_total{job=\"linux_vm\"}) ) * 100 ",
      "format": "table",
      "hide": false,
      "legendFormat": "CPU",
      "range": true,
      "refId": "B"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "djoI8bg4k"
      },
      "editorMode": "code",
      "expr": "((((sum by (instance) (node_memory_MemTotal_bytes{job=\"linux_vm\"})) - (sum by (instance)(node_memory_MemFree_bytes{job=\"linux_vm\"}))) / (sum by (instance) (node_memory_MemTotal_bytes{job=\"linux_vm\"}))) * 100)",
      "format": "table",
      "hide": false,
      "legendFormat": "Memory",
      "range": true,
      "refId": "A"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "djoI8bg4k"
      },
      "editorMode": "code",
      "expr": "((((sum by (instance) (node_filesystem_size_bytes{job=\"linux_vm\"})) - (sum by (instance) (node_filesystem_free_bytes{job=\"linux_vm\"}))) / (sum by (instance) (node_filesystem_size_bytes{job=\"linux_vm\"}))) * 100)",
      "format": "table",
      "hide": false,
      "legendFormat": "Disk",
      "range": true,
      "refId": "C"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "djoI8bg4k"
      },
      "editorMode": "code",
      "expr": " sum by (instance)(count without (job,mode) (node_cpu_seconds_total{job=\"linux_vm\",mode=\"idle\"}))",
      "format": "table",
      "hide": false,
      "range": true,
      "refId": "E"
    }
  ],
  "title": "Server Capacity",
  "transformations": [
    {
      "id": "merge",
      "options": {}
    },
    {
      "id": "groupBy",
      "options": {
        "fields": {
          "Value #A": {
            "aggregations": [
              "lastNotNull"
            ],
            "operation": "aggregate"
          },
          "Value #B": {
            "aggregations": [
              "lastNotNull"
            ],
            "operation": "aggregate"
          },
          "Value #C": {
            "aggregations": [
              "lastNotNull"
            ],
            "operation": "aggregate"
          },
          "Value #E": {
            "aggregations": [
              "lastNotNull"
            ],
            "operation": "aggregate"
          },
          "instance": {
            "aggregations": [],
            "operation": "groupby"
          }
        }
      }
    },
    {
      "id": "organize",
      "options": {
        "excludeByName": {},
        "indexByName": {
          "Value #A (lastNotNull)": 3,
          "Value #B (lastNotNull)": 2,
          "Value #C (lastNotNull)": 4,
          "Value #E (lastNotNull)": 1,
          "instance": 0
        },
        "renameByName": {
          "Value #A (lastNotNull)": "RAM",
          "Value #B (lastNotNull)": "CPU Load",
          "Value #C (lastNotNull)": "Disk Usage",
          "Value #E (lastNotNull)": "Cores",
          "instance": "Node"
        }
      }
    }
  ],
  "type": "table"
}
