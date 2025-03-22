---
UID: NE:classpnp.FAILURE_PREDICTION_METHOD
tech.root: kernel
title: FAILURE_PREDICTION_METHOD
ms.date: 03/11/2024
targetos: Windows
description: 
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: classpnp.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: true
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - classpnp.h
api_name:
 - FAILURE_PREDICTION_METHOD
 - PFAILURE_PREDICTION_METHOD
f1_keywords:
 - FAILURE_PREDICTION_METHOD
 - classpnp/FAILURE_PREDICTION_METHOD
 - PFAILURE_PREDICTION_METHOD
 - classpnp/PFAILURE_PREDICTION_METHOD
dev_langs:
 - c++
helpviewer_keywords:
 - FAILURE_PREDICTION_METHOD
---

# FAILURE_PREDICTION_METHOD enumeration (classpnp.h)

## -description

The **FAILURE_PREDICTION_METHOD** enum specifies which method to use for failure prediction.

## -enum-fields

### -field FailurePredictionNone

Specifies that no failure detection polling is needed.

### -field FailurePredictionIoctl

Specifies to do failure detection via IOCTL.

### -field FailurePredictionSmart

Specifies to do failure detection via SMART.

### -field FailurePredictionSense

Specifies to do failure detection via sense data.

## -remarks

## -see-also
