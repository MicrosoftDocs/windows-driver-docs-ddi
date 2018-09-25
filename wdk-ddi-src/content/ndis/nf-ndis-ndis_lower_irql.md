---
UID: NF:ndis.NDIS_LOWER_IRQL
title: NDIS_LOWER_IRQL macro
author: windows-driver-content
description: The NDIS_LOWER_IRQL macro sets the IRQL on the current processor to the specified value.
tech.root: netvista
ms.assetid: 378ea89f-cad9-410d-88b3-14bd1109e399
ms.author: windowsdriverdev
ms.date: 04/16/2018
ms.topic: macro
ms.keywords: NDIS_LOWER_IRQL
req.header: ndis.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: Any level (see Remarks section)
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
-	NDIS_LOWER_IRQL
product:
-	Windows
targetos: Windows

---

# NDIS_LOWER_IRQL macro


## -description

The NDIS_LOWER_IRQL macro sets the IRQL on the current processor to the specified value.

## -parameters

### -param _OldIrql_

The original (that is, unraised) IRQL value from before the driver called the [**NDIS_RAISE_IRQL_TO_DISPATCH**](nf-ndis-ndis_raise_irql_to_dispatch.md) macro. **NDIS_LOWER_IRQL** sets the IRQL to this value.

### -param _CurIrql_

The current IRQL value that is active before the call to **NDIS_LOWER_IRQL**.

## -returns

This macro does not return a value.

## -remarks

NDIS network drivers should use the **NDIS_LOWER_IRQL** macro to restore the IRQL setting that existed before a call to the [**NDIS_RAISE_IRQL_TO_DISPATCH**](nf-ndis-ndis_raise_irql_to_dispatch.md) macro.

If the value that the *\_OldIrql\_* parameter specifies is not equal to the current IRQL, the **NDIS_LOWER_IRQL** macro attempts to lower the IRQL to the value that the *\_OldIrql\_* parameter specifies.

It is a fatal error to call **NDIS_LOWER_IRQL** and use a value for *\_OldIrql\_* that was not returned from an immediately preceding call to the [**NDIS_RAISE_IRQL_TO_DISPATCH**](nf-ndis-ndis_raise_irql_to_dispatch.md) macro.

**NDIS_LOWER_IRQL** is an NDIS wrapper for the [**KeLowerIrql**](../wdm/nf-wdm-kelowerirql.md) routine.

## -see-also

[**KeLowerIrql**](../wdm/nf-wdm-kelowerirql.md)

[**NDIS_RAISE_IRQL_TO_DISPATCH**](nf-ndis-ndis_raise_irql_to_dispatch.md)
