---
UID: NF:mcd.ChangerGetProductData
title: ChangerGetProductData function
author: windows-driver-content
description: ChangerGetProductData handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_GET_PRODUCT_DATA.
old-location: storage\changergetproductdata.htm
old-project: storage
ms.assetid: b2723a34-d9c2-40c9-b6c9-6441ead63d2e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ChangerGetProductData, ChangerGetProductData function [Storage Devices], chgrmini_05ad3aaa-8975-44ee-ad09-149f288d8eef.xml, mcd/ChangerGetProductData, storage.changergetproductdata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mcd.h
api_name:
-	ChangerGetProductData
product:
- Windows
targetos: Windows
req.typenames: 
---

# ChangerGetProductData function


## -description


<b>ChangerGetProductData</b> handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_GET_PRODUCT_DATA. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object that represents the changer. 


### -param Irp [in]

Pointer to the IRP. 


## -returns



<b>ChangerGetProductData</b> always returns STATUS_SUCCESS.




## -remarks



This routine is required.

<b>ChangerGetProductData</b> returns product data for a changer.

The changer class driver checks the output buffer length in the I/O stack location before calling <b>ChangerGetProductData</b>. If output buffer length is smaller than <b>sizeof</b>(CHANGER_PRODUCT_DATA) then the changer class driver returns with a value of STATUS_INFO_LENGTH_MISMATCH

<b>ChangerGetProductData</b> fills in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551475">CHANGER_PRODUCT_DATA</a> structure at <i>Irp</i><b>-&gt;AssociatedIrp.SystemBuffer</b> before returning to the changer class driver. If the miniclass driver cached inquiry data in the changer's device extension before returning from <b>ChangerInitialize</b>, all members except <b>DeviceType</b> can be filled in from this data. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551475">CHANGER_PRODUCT_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551431">ChangerInitialize</a>
 

 

