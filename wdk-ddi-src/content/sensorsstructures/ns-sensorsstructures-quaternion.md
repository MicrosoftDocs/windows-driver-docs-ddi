---
UID: NS:sensorsstructures.__unnamed_struct_4
title: QUATERNION (sensorsstructures.h)
description: A structure that represents a 4-dimensional vector used for simple 3D rotation operation.
ms.date: 10/19/2018
keywords: ["QUATERNION structure"]
tech.root: sensors
ms.keywords: QUATERNION, QUATERNION, *PQUATERNION,
req.header: sensorsstructures.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: QUATERNION, *PQUATERNION
targetos: Windows
ms.custom: RS5
f1_keywords:
 - PQUATERNION
 - sensorsstructures/PQUATERNION
 - QUATERNION
 - sensorsstructures/QUATERNION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sensorsstructures.h
api_name:
 - PQUATERNION
 - QUATERNION
product:
 - Windows
---

# QUATERNION structure


## -description

A structure that represents a 4-dimensional vector used for simple 3D rotation operation.

## -struct-fields

### -field X

Horizontal vector.

### -field Y

Vertical vector.

### -field Z

Vector on the Z-axis.

### -field W

## -remarks

The rotation is done around the axis formed by the vector v= [X, Y, Z] and is of angle ?, and we have:

>W=cos(theta/2) <br/>
>|v|=sin(theta/2)

## -see-also

