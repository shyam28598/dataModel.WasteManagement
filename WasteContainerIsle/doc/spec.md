Entity: WasteContainerIsle  
==========================  
[Open License](https://github.com/smart-data-models//dataModel.WasteManagement/blob/master/WasteContainerIsle/LICENSE.md)  
[document generated automatically](https://docs.google.com/presentation/d/e/2PACX-1vTs-Ng5dIAwkg91oTTUdt8ua7woBXhPnwavZ0FxgR8BsAI_Ek3C5q97Nd94HS8KhP-r_quD4H0fgyt3/pub?start=false&loop=false&delayms=3000#slide=id.gb715ace035_0_60)  
Global description: **A waste container isle**  

## List of properties  

- `address`: The mailing address  - `alternateName`: An alternative name for this item  - `areaServed`: The geographic area where a service or offered item is provided  - `dataProvider`: A sequence of characters identifying the provider of the harmonised data entity.  - `dateCreated`: Entity creation timestamp. This will usually be allocated by the storage platform.  - `dateModified`: Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.  - `description`: A description of this item  - `features`: A list of features provided by the isle.  - `id`: Unique identifier of the entity  - `insertHolesNumber`: Number of insert holes the isle has  - `location`: Geojson reference to the item. It can be Point, LineString, Polygon, MultiPoint, MultiLineString or MultiPolygon  - `name`: The name of this item.  - `owner`: A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)  - `refWasteContainer`: List of containers present in the isle  - `seeAlso`: list of uri pointing to additional resources about the item  - `source`: A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.  - `type`: NGSI Entity Type: It has to be WasteContainerIsle    
Required properties  
- `id`  - `location`  - `type`    
A geographical area which keeps one or more waste containers.  
## Data Model description of properties  
Sorted alphabetically (click for details)  
<details><summary><strong>full yaml details</strong></summary>    
```yaml  
WasteContainerIsle:    
  description: 'A waste container isle'    
  properties:    
    address:    
      description: 'The mailing address'    
      properties:    
        addressCountry:    
          description: 'Property. The country. For example, Spain. Model:''https://schema.org/addressCountry'''    
          type: string    
        addressLocality:    
          description: 'Property. The locality in which the street address is, and which is in the region. Model:''https://schema.org/addressLocality'''    
          type: string    
        addressRegion:    
          description: 'Property. The region in which the locality is, and which is in the country. Model:''https://schema.org/addressRegion'''    
          type: string    
        postOfficeBoxNumber:    
          description: 'Property. The post office box number for PO box addresses. For example, 03578. Model:''https://schema.org/postOfficeBoxNumber'''    
          type: string    
        postalCode:    
          description: 'Property. The postal code. For example, 24004. Model:''https://schema.org/https://schema.org/postalCode'''    
          type: string    
        streetAddress:    
          description: 'Property. The street address. Model:''https://schema.org/streetAddress'''    
          type: string    
      type: object    
      x-ngsi:    
        model: https://schema.org/address    
        type: Property    
    alternateName:    
      description: 'An alternative name for this item'    
      type: string    
      x-ngsi:    
        type: Property    
    areaServed:    
      description: 'The geographic area where a service or offered item is provided'    
      type: string    
      x-ngsi:    
        model: https://schema.org/Text    
        type: Property    
    dataProvider:    
      description: 'A sequence of characters identifying the provider of the harmonised data entity.'    
      type: string    
      x-ngsi:    
        type: Property    
    dateCreated:    
      description: 'Entity creation timestamp. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: string    
      x-ngsi:    
        type: Property    
    dateModified:    
      description: 'Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: string    
      x-ngsi:    
        type: Property    
    description:    
      description: 'A description of this item'    
      type: string    
      x-ngsi:    
        type: Property    
    features:    
      description: 'A list of features provided by the isle.'    
      items:    
        enum:    
          - containerFix    
          - underground    
          - fenced    
          - other    
        type: string    
      minItems: 1    
      type: array    
      uniqueItems: true    
      x-ngsi:    
        type: Property    
    id:    
      anyOf: &wastecontainerisle_-_properties_-_owner_-_items_-_anyof    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Unique identifier of the entity'    
      x-ngsi:    
        type: Property    
    insertHolesNumber:    
      description: 'Number of insert holes the isle has'    
      minimum: 0    
      type: number    
      x-ngsi:    
        model: https://schema.org/Number    
        type: Property    
    location:    
      description: 'Geojson reference to the item. It can be Point, LineString, Polygon, MultiPoint, MultiLineString or MultiPolygon'    
      oneOf:    
        - description: 'Geoproperty. Geojson reference to the item. Point'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                type: number    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - Point    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON Point'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. LineString'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - LineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON LineString'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. Polygon'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 4    
                type: array    
              type: array    
            type:    
              enum:    
                - Polygon    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON Polygon'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. MultiPoint'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiPoint    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiPoint'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. MultiLineString'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiLineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiLineString'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. MultiLineString'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    items:    
                      type: number    
                    minItems: 2    
                    type: array    
                  minItems: 4    
                  type: array    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiPolygon    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiPolygon'    
          type: object    
      x-ngsi:    
        type: Geoproperty    
    name:    
      description: 'The name of this item.'    
      type: string    
      x-ngsi:    
        type: Property    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *wastecontainerisle_-_properties_-_owner_-_items_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      type: array    
      x-ngsi:    
        type: Property    
    refWasteContainer:    
      description: 'List of containers present in the isle'    
      items:    
        anyOf: *wastecontainerisle_-_properties_-_owner_-_items_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      minItems: 1    
      type: array    
      uniqueItems: true    
      x-ngsi:    
        model: http://schema.org/URL.    
        type: Property    
    seeAlso:    
      description: 'list of uri pointing to additional resources about the item'    
      oneOf:    
        - items:    
            format: uri    
            type: string    
          minItems: 1    
          type: array    
        - format: uri    
          type: string    
      x-ngsi:    
        type: Property    
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: string    
      x-ngsi:    
        type: Property    
    type:    
      description: 'NGSI Entity Type: It has to be WasteContainerIsle'    
      enum:    
        - WasteContainerIsle    
      type: string    
      x-ngsi:    
        type: Property    
  required:    
    - id    
    - type    
    - location    
  type: object    
```  
</details>    
## Example payloads    
#### WasteContainerIsle NGSI-v2 key-values Example    
Here is an example of a WasteContainerIsle in JSON-LD format as key-values. This is compatible with NGSI-v2 when  using `options=keyValues` and returns the context data of an individual entity.  
```json  
{  
  "id": "wastecontainerisle:Fleming:12",  
  "type": "WasteContainerIsle",  
  "location": {  
    "type": "Polygon",  
    "coordinates": [  
      [  
        [-3.164485591715449, 40.62785133667262],  
        [-3.164445130316209, 40.627871567372239],  
        [-3.164394553567159, 40.627772099765778],  
        [-3.164424899616589, 40.62775018317452],  
        [-3.164485591715449, 40.62785133667262]  
      ]  
    ]  
  },  
  "address": {  
    "streetAddress": "Calle Dr. Fleming, 12",  
    "addressLocality": "Guadalajara",  
    "addressCountry": "ES"  
  },  
  "features": ["underground"],  
  "name": "Dr. Fleming 12, Esquina Manuel Paez Xaramillo",  
  "description": "Container isle located downtown",  
  "refWasteContainer": [  
    "wastecontainer:Fleming:12a",  
    "wastecontainer:Fleming:12b"  
  ]  
}  
```  
#### WasteContainerIsle NGSI-v2 normalized Example    
Here is an example of a WasteContainerIsle in JSON-LD format as normalized. This is compatible with NGSI-v2 when not using options and returns the context data of an individual entity.  
```json  
{  
  "id": "wastecontainerisle:Fleming:12",  
  "type": "WasteContainerIsle",  
  "refWasteContainer": {  
    "type": "Relationship",  
    "value": ["wastecontainer:Fleming:12a", "wastecontainer:Fleming:12b"]  
  },  
  "features": {  
    "type": "array",  
    "value": ["underground"]  
  },  
  "description": {  
    "type": "Text",  
    "value": "Container isle located downtown"  
  },  
  "location": {  
    "type": "geo:json",  
    "value": {  
      "type": "Polygon",  
      "coordinates": [  
        [  
          [-3.164485591715449, 40.62785133667262],  
          [-3.164445130316209, 40.62787156737224],  
          [-3.164394553567159, 40.62777209976578],  
          [-3.164424899616589, 40.62775018317452],  
          [-3.164485591715449, 40.62785133667262]  
        ]  
      ]  
    }  
  },  
  "address": {  
    "type": "PostalAddress",  
    "value": {  
      "addressLocality": "Guadalajara",  
      "addressCountry": "ES",  
      "streetAddress": "Calle Dr. Fleming, 12"  
    }  
  },  
  "name": {  
    "type": "Text",  
    "value": "Dr. Fleming 12, Esquina Manuel Paez Xaramillo"  
  }  
}  
```  
#### WasteContainerIsle NGSI-LD key-values Example    
Here is an example of a WasteContainerIsle in JSON-LD format as key-values. This is compatible with NGSI-LD when  using `options=keyValues` and returns the context data of an individual entity.  
```json  
{  
  "@context": [  
    "https://smartdatamodels.org/context.jsonld",  
    "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
  ],  
  "address": {  
    "addressCountry": "ES",  
    "addressLocality": "Guadalajara",  
    "streetAddress": "Calle Dr. Fleming, 12",  
    "type": "PostalAddress"  
  },  
  "description": "Container isle located downtown",  
  "features": [  
    "underground"  
  ],  
  "id": "urn:ngsi-ld:WasteContainerIsle:wastecontainerisle:Fleming:12",  
  "location": {  
    "coordinates": [  
      [  
        [  
          -3.164485591715449,  
          40.62785133667262  
        ],  
        [  
          -3.164445130316209,  
          40.62787156737224  
        ],  
        [  
          -3.164394553567159,  
          40.62777209976578  
        ],  
        [  
          -3.164424899616589,  
          40.62775018317452  
        ],  
        [  
          -3.164485591715449,  
          40.62785133667262  
        ]  
      ]  
    ],  
    "type": "Polygon"  
  },  
  "name": "Dr. Fleming 12, Esquina Manuel Paez Xaramillo",  
  "refWasteContainer": [  
    "urn:ngsi-ld:WasteContainer:wastecontainer:Fleming:12a",  
    "urn:ngsi-ld:WasteContainer:wastecontainer:Fleming:12b"  
  ],  
  "type": "WasteContainerIsle"  
}  
```  
#### WasteContainerIsle NGSI-LD normalized Example    
Here is an example of a WasteContainerIsle in JSON-LD format as normalized. This is compatible with NGSI-LD when not using options and returns the context data of an individual entity.  
```json  
{  
  "id": "urn:ngsi-ld:WasteContainerIsle:wastecontainerisle:Fleming:12",  
  "type": "WasteContainerIsle",  
  "refWasteContainer": {  
    "type": "Relationship",  
    "object": [  
      "urn:ngsi-ld:WasteContainer:wastecontainer:Fleming:12a",  
      "urn:ngsi-ld:WasteContainer:wastecontainer:Fleming:12b"  
    ]  
  },  
  "features": {  
    "type": "Property",  
    "value": [  
      "underground"  
    ]  
  },  
  "description": {  
    "type": "Property",  
    "value": "Container isle located downtown"  
  },  
  "location": {  
    "type": "GeoProperty",  
    "value": {  
      "type": "Polygon",  
      "coordinates": [  
        [  
          [  
            -3.164485591715449,  
            40.62785133667262  
          ],  
          [  
            -3.164445130316209,  
            40.62787156737224  
          ],  
          [  
            -3.164394553567159,  
            40.62777209976578  
          ],  
          [  
            -3.164424899616589,  
            40.62775018317452  
          ],  
          [  
            -3.164485591715449,  
            40.62785133667262  
          ]  
        ]  
      ]  
    }  
  },  
  "address": {  
    "type": "Property",  
    "value": {  
      "addressLocality": "Guadalajara",  
      "addressCountry": "ES",  
      "streetAddress": "Calle Dr. Fleming, 12",  
      "type": "PostalAddress"  
    }  
  },  
  "name": {  
    "type": "Property",  
    "value": "Dr. Fleming 12, Esquina Manuel Paez Xaramillo"  
  },  
  "@context": [  
    "https://smartdatamodels.org/context.jsonld",  
    "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
  ]  
}  
```  
