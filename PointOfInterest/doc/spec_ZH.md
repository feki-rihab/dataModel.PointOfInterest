<!-- 10-Header -->
[![Smart Data Models](https://smartdatamodels.org/wp-content/uploads/2022/01/SmartDataModels_logo.png "Logo")](https://smartdatamodels.org)  

======================
<!-- 15-License -->


<!-- /15-License -->
<!-- 20-Description -->


<!-- /20-Description -->
<!-- 30-PropertiesList -->




- `additionalInfoURL[*]`: 可以获得该主题的其他信息的URL  
<!-- 35-RequiredProperties -->

- `category`  
<!-- 40-RequiredProperties -->

<!-- /40-RequiredProperties -->
<!-- 50-DataModelHeader -->


<!-- /50-DataModelHeader -->
<!-- 60-ModelYaml -->
<details><summary><strong>full yaml details</strong></summary>    

PointOfInterest:    
  description: 'This entity contains a harmonised geographic description of a Point of Interest'    
  properties:    
    additionalInfoURL:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'URL from which additional information of the subject can be obtained'    
      x-ngsi:    
        type: Relationship    
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
    category:    
      description: 'Category of this point of interest. Allowed values: Those defined by the [Factual taxonomy](https://github.com/Factual/places/blob/master/categories/factual_taxonomy.json) together with the extended categories described by the specification. For instance the value `113` corresponds to beaches, and the value `311` corresponds to museums.'    
      items:    
        type: string    
      minItems: 1    
      type: array    
      x-ngsi:    
        model: https://schema.org/Text    
        type: Property    
    contactPoint:    
      description: 'The details to contact with the item.'    
      properties:    
        contactType:    
          description: 'Property. Contact type of this item.'    
          type: string    
        email:    
          description: 'Property. Email address of owner.'    
          format: idn-email    
          type: string    
        name:    
          description: 'Property. The name of this item.'    
          type: string    
        telephone:    
          description: 'Property. Telephone of this contact.'    
          type: string    
        url:    
          description: 'Property. URL which provides a description or further information about this item.'    
          format: uri    
          type: string    
      type: object    
      x-ngsi:    
        model: https://schema.org/ContactPoint    
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
    id:    
      anyOf: &pointofinterest_-_properties_-_owner_-_items_-_anyof    
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
        anyOf: *pointofinterest_-_properties_-_owner_-_items_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      type: array    
      x-ngsi:    
        type: Property    
    refSeeAlso:    
      description: 'List of references to one or more related entities.'    
      items:    
        anyOf:    
          - anyOf: *pointofinterest_-_properties_-_owner_-_items_-_anyof    
            description: 'Property. Unique identifier of the entity'    
      minItems: 1    
      type: array    
      uniqueItems: true    
      x-ngsi:    
        model: https://schema.org/URL    
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
      description: 'NGSI Entity type. It has to be PointOfInterest'    
      enum:    
        - PointOfInterest    
      type: string    
      x-ngsi:    
        type: Property    
    wardId:    
      description: 'Ward ID of the entity corresponding to this observation.'    
      type: string    
      x-ngsi:    
        type: Property    
    zoneId:    
      description: 'Zone ID of the entity corresponding to this observation.'    
      type: string    
      x-ngsi:    
        type: Property    
    zoneName:    
      description: 'Zone name of the entity corresponding to this observation.'    
      type: string    
      x-ngsi:    
        type: Property    
  required:    
    - id    
    - type    
    - category    
    - name    
  type: object    
  x-derived-from: ""    
  x-disclaimer: 'Redistribution and use in source and binary forms, with or without modification, are permitted  provided that the license conditions are met. Copyleft (c) 2021 Contributors to Smart Data Models Program'    
  x-license-url: https://github.com/smart-data-models/dataModel.PointOfInterest/blob/master/PointOfInterest/LICENSE.md    
  x-model-schema: https://smart-data-models.github.io/dataModel.PointOfInterest/PointOfInterest/schema.json    
  x-model-tags: IUDX    
  x-version: 0.2.0    
```  
</details>    
<!-- /60-ModelYaml -->
<!-- 70-MiddleNotes -->
<!-- /70-MiddleNotes -->
<!-- 80-Examples -->



<details><summary><strong>show/hide example</strong></summary>    


  "id": "urn:ngsi-ld:PointOfInterest-A-Concha-123456",  
  "type": "PointOfInterest",  
  "name": "Playa de a Concha",  
  "description": "La Playa de A Concha se presenta como una continuación de la Playa de Compostela, una de las más frecuentadas de Vilagarcía.",  
  "address": {  
    "addressCountry": "ES",  
    "addressLocality": "Vilagarcía de Arousa"  
  },  
  "category": [  
    "113"  
  ],  
  "location": {  
    "type": "Point",  
    "coordinates": [  
      -8.768460000000001,  
      42.60214472222222  
    ]  
  },  
  "source": "http://www.tourspain.es",  
  "refSeeAlso": [  
    "Beach-A-Concha-123456"  
  ],  
  "wardId": "",  
  "zoneId": "",  
  "additionalInfoURL": "urn:ngsi-ld:Point:34E4:A234",  
  "zoneName": ""  
}  
```  
</details>  


<details><summary><strong>show/hide example</strong></summary>    


  "id": "PointOfInterest-A-Concha-123456",  
  "type": "PointOfInterest",  
  "category": {  
    "type": "array",  
    "value": [  
      "113"  
    ]  
  },  
  "description": {  
    "type": "Text",  
    "value": "La Playa de A Concha se presenta como una continuaciin de la Playa de Compostela, una de las mis frecuentadas de Vilagarcia."  
  },  
  "refSeeAlso": {  
    "type": "array",  
    "value": [  
      "Beach-A-Concha-123456"  
    ]  
  },  
  "source": {  
    "type": "Text",  
    "value": "http://www.tourspain.es"  
  },  
  "location": {  
    "type": "geo:json",  
    "value": {  
      "type": "Point",  
      "coordinates": [  
        -8.768460000000001,  
        42.60214472222222  
      ]  
    }  
  },  
  "address": {  
    "type": "PostalAddress",  
    "value": {  
      "addressCountry": "ES",  
      "addressLocality": "Vilagarcia de Arousa"  
    }  
  },  
  "name": {  
    "type": "Text",  
    "value": "Playa de a Concha"  
  },  
  "wardId": {  
    "type": "Text",  
    "value": ""  
  },  
  "zoneId": {  
    "type": "Text",  
    "value": ""  
  },  
  "additionalInfoURL": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:Point:34E4:A234"  
  },  
  "zoneName": {  
    "type": "Text",  
    "value": ""  
  }  
}  
```  
</details>  


<details><summary><strong>show/hide example</strong></summary>    


    "id": "urn:ngsi-ld:PointOfInterest:PointOfInterest-A-Concha-123456",  
    "type": "PointOfInterest",  
    "additionalInfoURL": "urn:ngsi-ld:Point:34E4:A234",  
    "address": {  
        "addressCountry": "ES",  
        "addressLocality": "Vilagarcia de Arousa"  
    },  
    "category": [  
        "113"  
    ],  
    "description": "La Playa de A Concha se presenta como una continuacion de la Playa de Compostela, una de las mas frecuentadas de Vilagarcia.",  
    "location": {  
        "type": "Point",  
        "coordinates": [  
            -8.768460000000001,  
            42.60214472222222  
        ]  
    },  
    "name": "Playa de a Concha",  
    "refSeeAlso": [  
        "urn:ngsi-ld:SeeAlso:Beach-A-Concha-123456"  
    ],  
    "source": "http://www.tourspain.es",  
    "wardId": "",  
    "zoneId": "",  
    "zoneName": "",  
    "@context": [  
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld",  
        "https://raw.githubusercontent.com/smart-data-models/dataModel.PointOfInterest/master/context.jsonld"  
    ]  
}  
```  
</details>  


<details><summary><strong>show/hide example</strong></summary>    


    "id": "urn:ngsi-ld:PointOfInterest:PointOfInterest-A-Concha-123456",  
    "type": "PointOfInterest",  
    "additionalInfoURL": {  
        "type": "Relationship",  
        "value": "urn:ngsi-ld:Point:34E4:A234"  
    },  
    "address": {  
        "type": "Property",  
        "value": {  
            "addressCountry": "ES",  
            "addressLocality": "Vilagarcia de Arousa"  
        }  
    },  
    "category": {  
        "type": "Property",  
        "value": [  
            "113"  
        ]  
    },  
    "description": {  
        "type": "Property",  
        "value": "La Playa de A Concha se presenta como una continuacion de la Playa de Compostela, una de las mas frecuentadas de Vilagarcia."  
    },  
    "location": {  
        "type": "GeoProperty",  
        "value": {  
            "type": "Point",  
            "coordinates": [  
                -8.768460000000001,  
                42.60214472222222  
            ]  
        }  
    },  
    "name": {  
        "type": "Property",  
        "value": "Playa de a Concha"  
    },  
    "refSeeAlso": {  
        "type": "Property",  
        "value": [  
            "urn:ngsi-ld:SeeAlso:Beach-A-Concha-123456"  
        ]  
    },  
    "source": {  
        "type": "Property",  
        "value": "http://www.tourspain.es"  
    },  
    "wardId": {  
        "type": "Property",  
        "value": ""  
    },  
    "zoneId": {  
        "type": "Property",  
        "value": ""  
    },  
    "zoneName": {  
        "type": "Property",  
        "value": ""  
    },  
    "@context": [  
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld",  
        "https://raw.githubusercontent.com/smart-data-models/dataModel.PointOfInterest/master/context.jsonld"  
    ]  
}  
```  
</details><!-- /80-Examples -->
<!-- 90-FooterNotes -->
<!-- /90-FooterNotes -->
<!-- 95-Units -->

<!-- /95-Units -->
<!-- 97-LastFooter -->
---  
