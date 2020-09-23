---
UID: NE:ntddk._BDCB_CALLBACK_TYPE
title: _BDCB_CALLBACK_TYPE (ntddk.h)
description: The BDCB_CALLBACK_TYPE enumeration specifies whether the callback being passed to a BOOT_DRIVER_CALLBACK_FUNCTION routine is a status update or a boot-start driver initialization notification.
old-location: kernel\bdcb_callback_type.htm
tech.root: kernel
ms.assetid: 22698DF4-7B8C-40B8-9B07-EEDCC03D0D0F
ms.date: 04/30/2018
keywords: ["BDCB_CALLBACK_TYPE enumeration"]
ms.keywords: "*PBDCB_CALLBACK_TYPE, BDCB_CALLBACK_TYPE, BDCB_CALLBACK_TYPE enumeration [Kernel-Mode Driver Architecture], BdCbInitializeImage, BdCbStatusUpdate, _BDCB_CALLBACK_TYPE, kernel.bdcb_callback_type, ntddk/BDCB_CALLBACK_TYPE, ntddk/BdCbInitializeImage, ntddk/BdCbStatusUpdate"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 8.
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
req.irql: 
targetos: Windows
req.typenames: BDCB_CALLBACK_TYPE, *PBDCB_CALLBACK_TYPE
f1_keywords:
 - _BDCB_CALLBACK_TYPE
 - ntddk/_BDCB_CALLBACK_TYPE
 - PBDCB_CALLBACK_TYPE
 - ntddk/PBDCB_CALLBACK_TYPE
 - BDCB_CALLBACK_TYPE
 - ntddk/BDCB_CALLBACK_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - BDCB_CALLBACK_TYPE
---

# _BDCB_CALLBACK_TYPE enumeration


## -description

The BDCB_CALLBACK_TYPE enumeration specifies  whether the callback being passed to a <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioregisterbootdrivercallback">BOOT_DRIVER_CALLBACK_FUNCTION</a> routine is a status update or a boot-start driver initialization notification.

## -enum-fields

### -field BdCbStatusUpdate

A status update provided by the system to a boot-start driver.

### -field BdCbInitializeImage

A boot image is about to be initialized. During this callback, boot-start drivers may classify a boot image as a known good image or a known bad image.

## -remarks

The two callback types have unique context structures that provide additional information specific to the callback.

<table>
<tr>
<th>Value </th>
<th>Corresponding structure to use</th>
</tr>
<tr>
<td>
BdCbStatusUpdate

</td>
<td>

<a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_bdcb_status_update_type">BDCB_STATUS_UPDATE_TYPE</a>


</td>
</tr>
<tr>
<td>
BdCbInitializeImage

</td>
<td>

<a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_bdcb_classification">BDCB_CLASSIFICATION</a>


</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_bdcb_classification">BDCB_CLASSIFICATION</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_bdcb_status_update_type">BDCB_STATUS_UPDATE_TYPE</a>



[**BOOT_DRIVER_CALLBACK_FUNCTION**](nc-ntddk-boot_driver_callback_function.md)