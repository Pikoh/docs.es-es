---
title: propiedad de clave externa
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 044be77cbbd8b5ad16cfbd5bbf1fdde984a060d5
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="foreign-key-property"></a>propiedad de clave externa
A *propiedad de clave externa* en Entity Data Model (EDM) es un tipo primitivo [propiedad](../../../../docs/framework/data/adonet/property.md) (o un conjunto de propiedades de tipo primitivo) en un [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md) que contiene el [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) de otro tipo de entidad.  
  
 Una propiedad de clave externa es análoga a una columna de clave externa de una base de datos relacional. En la misma manera que se usan columnas de clave externa en una base de datos relacional para crear relaciones entre filas de tablas, las propiedades de clave externa en un modelo conceptual se usan para establecer [asociaciones](../../../../docs/framework/data/adonet/association-type.md) entre tipos de entidad. A [restricción de integridad referencial](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) se utiliza para definir una asociación entre dos tipos de entidad cuando uno de ellos tiene una propiedad de clave externa.  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`. El tipo de entidad `Book` tiene una propiedad, `PublisherId`, que hace referencia a la clave de entidad del tipo de entidad `Publisher` cuando se define una restricción de integridad referencial en la asociación `PublishedBy`.  
  
 ![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")  
  
 El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. El código CSDL siguiente usa la propiedad de clave externa `PublisherId` para definir una restricción de integridad referencial en la asociación `PublishedBy` incluida en el modelo conceptual mostrado anteriormente.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
