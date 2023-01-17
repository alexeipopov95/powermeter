# Powermeter

## Endpoints

------------------------------------------------------------------------------------------

#### Lister todos los medidores

<details>
 <summary><code>GET</code> <code><b>/meters/</b></code></summary>

##### Parameters

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | N/A      |  N/A | N/A   | N/A  |


##### Responses

> | http code    | content-type                      | response |
> |---------------|----------|---------------------------------------------------------------------|
> | `200`        | `application/json`        | JSON  |                         |
                                                             |

##### Example cURL

> ```bash
>  curl -X GET http://127.0.0.1:8000/meters/
> ```

</details>


#### Obtener un medidor en particular

<details>
 <summary><code>GET</code> <code><b>/meters/METER_KEY/</b></code></summary>

##### Parameters

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | N/A      |  N/A | N/A   | N/A  |


##### Responses

> | http code    | content-type                      | response |
> |---------------|----------|---------------------------------------------------------------------|
> | `200`        | `application/json`        | JSON  |   |

##### Example cURL

> ```bash
>  curl -X GET http://127.0.0.1:8000/meters/meter123/
> ```

</details>


#### Create un medidor

<details>
 <summary><code>POST</code> <code><b>/meters/</b></code></summary>

##### Parameters

> | name              |  type     | data type | description             |
> |-------------------|-----------|-------------------------|-------------------------------------|
> | `meter_key` |  required | str       | clave unica del medidor |
> | `name` |  required | str       | nombre del medidor      |


##### Responses

> | http code | content-type        | response| 
> |-----------|---------------------|---------|
> | `201`     | `application/json`  | JSON  |

##### Example cURL

> ```bash
>  curl -X POST -H 'Content-Type: application/json' -d '{"meter_key":"<METER-KEY>","name":"<NAME>"}' http://127.0.0.1:8000/meters/
> ```

</details>

#### Actualizar un medidor

<details>
 <summary><code>PUT/PATCH</code> <code><b>/meters/METERKEY/</b></code></summary>

##### Parameters

> | name              |  type     | data type | description             |
> |-------------------|-----------|-------------------------|-------------------------------------|
> | `meter_key` |  required | str       | clave unica del medidor |
> | `name` |  required | str       | nombre del medidor      |


##### Responses

> | http code | content-type        | response | 
> |---------------------|-----------|---------------------|
> | `200`     | `application/json`  | JSON  |

##### Example cURL

> ```bash
>  curl -X PUT -H 'Content-Type: application/json' -d '{"meter_key":"<METER-KEY>","name":"<NAME>"}' http://127.0.0.1:8000/meters/<METER-KEY>/
> ```

> ```bash
>  curl -X PATCH -H 'Content-Type: application/json' -d '{"meter_key":"<METER-KEY>"}' http://127.0.0.1:8000/meters/<METER-KEY>/
> ```

</details>


#### Eliminar un medidor

<details>
 <summary><code>DELETE</code> <code><b>/meters/METERKEY/</b></code></summary>

##### Parameters

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | N/A      |  N/A | N/A   | N/A  |


##### Responses

> | http code | content-type       | response | 
> |-----------|---------------------|-----------|
> | `204`     | `application/json` | JSON  |

##### Example cURL

> ```bash
>  curl -X DELETE http://127.0.0.1:8000/meters/<METER-KEY>/
> ```

</details>


#### Agregar una medida

<details>
 <summary><code>POST</code> <code><b>/meters/METERKEY/add_measure/</b></code></summary>

##### Parameters

> | name              |  type     | data type | description           |
> |-------------------|-----------|-----------------------|---|
> | `consumption` |  required | int       | medida positiva del medidor |



##### Responses

> | http code | content-type        | response | 
> |-----------|---------------------|-----------|
> | `201`     | `application/json`  | JSON  |

##### Example cURL

> ```bash
>  curl -X POST -H 'Content-Type: application/json' -d '{"consumption": 10}' http://127.0.0.1:8000/meters/<METER-KEY>/add_measure/
> ```


</details>


#### Consumo promedio del medidor

<details>
 <summary><code>GET</code> <code><b>/meters/METERKEY/avg_consumption/</b></code></summary>

##### Parameters

> | name |  type     | data type | description  |
> |-------|-----|--------------|-----------|
> | N/A |  N/A | N/A | N/A          |



##### Responses

> | http code | content-type        | response | 
> |-----------|-----------|---------------------|
> | `200`     | `application/json`  | JSON  |

##### Example cURL

> ```bash
>  curl -X GET http://127.0.0.1:8000/meters/<METER-KEY>/avg_consumption/
> ```


</details>


#### Consumo máximo del medidor

<details>
 <summary><code>GET</code> <code><b>/meters/METERKEY/max_consumption/</b></code></summary>

##### Parameters

> | name |  type     | data type | description  |
> |-------|-----|--------------|-----------|
> | N/A |  N/A | N/A | N/A          |



##### Responses

> | http code | content-type        | response | 
> |-----------|-----------|---------------------|
> | `200`     | `application/json`  | JSON  |

##### Example cURL

> ```bash
>  curl -X GET http://127.0.0.1:8000/meters/<METER-KEY>/max_consumption/
> ```


</details>

#### Consumo mínimo del medidor

<details>
 <summary><code>GET</code> <code><b>/meters/METERKEY/min_consumption/</b></code></summary>

##### Parameters

> | name |  type     | data type | description  |
> |-------|-----|--------------|-----------|
> | N/A |  N/A | N/A | N/A          |



##### Responses

> | http code | content-type        | response | 
> |-----------|-----------|---------------------|
> | `200`     | `application/json`  | JSON  |

##### Example cURL

> ```bash
>  curl -X GET http://127.0.0.1:8000/meters/<METER-KEY>/min_consumption/
> ```


</details>

#### Consumo total del medidor

<details>
 <summary><code>GET</code> <code><b>/meters/METERKEY/total_consumption/</b></code></summary>

##### Parameters

> | name |  type     | data type | description  |
> |-------|-----|--------------|-----------|
> | N/A |  N/A | N/A | N/A          |



##### Responses

> | http code | content-type        | response | 
> |-----------|-----------|---------------------|
> | `200`     | `application/json`  | JSON  |

##### Example cURL

> ```bash
>  curl -X GET http://127.0.0.1:8000/meters/<METER-KEY>/total_consumption/
> ```


</details>

------------------------------------------------------------------------------------------

