---
UID: NF:storport.StorPortSetUnitAttributes
title: StorPortSetUnitAttributes function (storport.h)
description: Learn more about the StorPortSetUnitAttributes routine.
tech.root: storage
ms.date: 06/13/2023
keywords: ["StorPortSetUnitAttributes function"]
ms.keywords: StorPortSetUnitAttributes, StorPortSetUnitAttributes routine [Storage Devices], storage.storportsetunitattributes, storport/StorPortSetUnitAttributes
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortSetUnitAttributes
 - storport/StorPortSetUnitAttributes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Storport.h
api_name:
 - StorPortSetUnitAttributes
---

# StorPortSetUnitAttributes function

## -description

The **StorPortSetUnitAttributes** routine registers attributes of a storage unit device with the Storport driver.

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param Address [in]

A [**STOR_ADDRESS**](ns-storport-_stor_address.md) structure that holds the storage unit device address. This parameter must not be NULL.

### -param Attributes [in]

A [**STOR_UNIT_ATTRIBUTES**](ns-storport-_stor_unit_attributes.md) structure with bits set to indicate the attributes supported for the unit device.

## -returns

**StorPortSetUnitAttributes** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The routine set the unit attributes successfully. |
| STOR_STATUS_INVALID_PARAMETER | One more more parameters are invalid. |

An invalid parameter can be any of the following:

* The **HwDeviceExtension** pointer is NULL.
* One or more reserved bits in **Attributes** are set.
* The unit address in **Address** is formatted incorrectly.
* A unit device is not found for the address given in **Address**.

## -remarks

A miniport driver calls this routine to register the unit attributes with Storport during completion of an SRB containing a SCSIOP_INQUIRY command request. The bits in **attributes** are set based on the data returned from the adapter for the inquiry command. Storport issues an inquiry for the unit at **Address** during a bus enumeration.

## -see-also

[**STOR_ADDRESS**](ns-storport-_stor_address.md)

[**STOR_UNIT_ATTRIBUTES**](ns-storport-_stor_unit_attributes.md)
