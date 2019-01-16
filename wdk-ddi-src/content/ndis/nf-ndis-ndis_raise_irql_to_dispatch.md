---
UID: NF:ndis.NDIS_RAISE_IRQL_TO_DISPATCH
title: NDIS_RAISE_IRQL_TO_DISPATCH macro
description: The NDIS_RAISE_IRQL_TO_DISPATCH macro raises the current IRQL to DISPATCH_LEVEL on the current processor.
tech.root: netvista
ms.assetid: e8078346-7fc7-4dee-9d39-b52c3ecb5415
ms.date: 04/16/2018
ms.topic: macro
ms.keywords: NDIS_RAISE_IRQL_TO_DISPATCH
req.header: ndis.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance: Irql_IrqlSetting_Function
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ndis.h
api_name: 
-	NDIS_RAISE_IRQL_TO_DISPATCH
product:
-	Windows
targetos: Windows

---

# NDIS_RAISE_IRQL_TO_DISPATCH macro


## -description

The **NDIS_RAISE_IRQL_TO_DISPATCH** macro raises the current IRQL to DISPATCH_LEVEL on the current processor.

## -parameters

### -param _pIrql_

A pointer to a KIRQL-type variable where **NDIS_RAISE_IRQL_TO_DISPATCH** stores the original (that is, unraised) IRQL value. You should use this original IRQL value in a subsequent call to the [**NDIS_LOWER_IRQL**](nf-ndis-ndis_lower_irql.md) macro.

## -returns

This macro does not return a value.

## -remarks

NDIS network drivers should use the **NDIS_RAISE_IRQL_TO_DISPATCH** macro to raise the current IRQL.

If the current IRQL is greater than DISPATCH_LEVEL, a bugcheck occurs. Otherwise, the macro sets the current IRQL to DISPATCH_LEVEL.

**NDIS_RAISE_IRQL_TO_DISPATCH** is an NDIS wrapper for the [**KeRaiseIrql**](../wdm/nf-wdm-keraiseirql.md) routine.

The caller should call the [**NDIS_LOWER_IRQL**](nf-ndis-ndis_lower_irql.md) macro to restore the original IRQL as soon as possible.

## -see-also

[**KeRaiseIrql**](../wdm/nf-wdm-keraiseirql.md)

[**NDIS_LOWER_IRQL**](nf-ndis-ndis_lower_irql.md)
