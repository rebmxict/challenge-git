# User cart actions

## Get authentication token

```http
GET /api/gserve/1/auth
```

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `auth_token` | `String` | `Bearer <auth_token>` |


-----


## Upload file and generate preview and stl files

```http
POST /api/gserve/1/file
```

### Request parameters
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `fileObject` | `File` | `STL or STEP file` |

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `uuid` | `String` |  |

### Errors
#### 400
Number of `CLOSED_SHELL` > 1 ? `A multi-body part`
Number of `CLOSED_SHELL` == 0 ? `A geometry is not detected in this file.`


-----


## Get features json file

```http
GET /api/gserve/1/file/data/<id>
```

### Request parameters
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `uuid` | `String` | `uuid` from `/api/gserve/1/file endpoint` |

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `file` | `File` | `features.json` file |


-----


## Get preview json file

```http
GET /api/gserve/1/file/preview/<id>
```

### Request parameters
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `uuid` | `String` | `uuid` from `/api/gserve/1/file endpoint` |

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `file` | `File` | `preview.json` file |


-----


## Get redacted step file

```http
GET /api/gserve/1/file/redact/<id>
```

### Request parameters
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `uuid` | `String` | `uuid` from `/api/gserve/1/file endpoint` |

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `file` | `File` | `redact.step` file |


-----


## Get original step file

```http
GET /api/gserve/1/file/original/<id>
```

### Request parameters
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `uuid` | `String` | `uuid` from `/api/gserve/1/file endpoint` |

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `file` | `File` | `original/original.step` file |


-----


## Get stl file

```http
GET /api/gserve/1/file/stl/<id>
```

### Request parameters
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `uuid` | `String` | `uuid` from `/api/gserve/1/file endpoint` |

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `file` | `File` | `preview.stl` file |


-----


## Generate specification file

```http
POST /api/gserve/1/file/specification/<id>
```

### Request parameters
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `uuid` | `String` | `uuid` from `/api/gserve/1/file endpoint` |
| `data` | `Object` |  |

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `file` | `File` | `specification.json` file |


-----


## Get specification file

```http
GET /api/gserve/1/file/specification/<id>
```

### Request parameters
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `uuid` | `String` | `uuid` from `/api/gserve/1/file endpoint` |

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `file` | `File` | `specification.json` file |


-----


## Get thunmbnail file

```http
GET /api/gserve/1/file/thumbnail/<id>
```

### Request parameters
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `uuid` | `String` | `uuid` from `/api/gserve/1/file endpoint` |

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `file` | `File` | `thumbnail.png` file |


-----


## Generate PDF file

```http
POST /api/gserve/1/file/generate-pdf/<id>
```

### Request parameters
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `uuid` | `String` | `uuid` from `/api/gserve/1/file endpoint` |
| `data` | `Object` | `List of PDF properties` |

**PDF properties**

| Field | Type | Info |
| :--- | :--- | :--- |
| `part_name` | `String` | `"test_file_000"` |
| `revision` | `String` | `"A"` |
| `id` | `String` | `"Q04579"` |
| `date` | `String` | `"08/07/2019"` |
| `material` | `String` | `"Metal - Aluminium - 6082 (Best for anodising)"` |
| `surface_finish` | `String` | `"As Machined"` |
| `hole_threading` | `String` | `""` |
| `max_roughness` | `String` | `"Ra 3.2 (+5% fee)"` |
| `min_tolerance` | `String` | `"+/- 0.127mm"` |
| `accreditation_req` | `String` | `"Not required"` |
| `notes` | `String` | `""` |
| `job_file` | `String` | `"https://app.geomiq.com/panel/vendor/job/detail?id=3236"` |

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `file` | `File` | `pdf` file |


-----


## IGS Redaction

```http
POST /api/gserve/1/redact-igs
```

### Request parameters
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `file` | `File` | `isg` file |

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `file` | `File` | Redacted igs file |


-----


## Get Stl bounding dimensions 

```http
POST /api/gserve/1/stl-bbox
```

### Request parameters
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `file` | `File` | `stl` file |

### Response
| Parameter | Type | Description |
| :--- | :--- | :--- |
| `data` | `Object` | Bounding dimensions |

**Bounding dimensions**

| Field | Type | Info |
| :--- | :--- | :--- |
| `bounding_box_x` | `Number` |  |
| `bounding_box_y` | `Number` |  |
| `bounding_box_z` | `Number` |  |


-----


## Upload apache log files 

```http
GET /api/gserve/1/logs
```


-----
