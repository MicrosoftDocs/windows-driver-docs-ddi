---
UID: NI:ntddchgr.IOCTL_CHANGER_GET_PRODUCT_DATA
title: IOCTL_CHANGER_GET_PRODUCT_DATA (ntddchgr.h)
description: Returns product data for the device.
old-location: storage\ioctl_changer_get_product_data.htm
tech.root: storage
ms.assetid: 2e3d0dbd-7d55-4241-9aea-f3474ab49025
ms.date: 03/29/2018
keywords: ["IOCTL_CHANGER_GET_PRODUCT_DATA IOCTL"]
ms.keywords: IOCTL_CHANGER_GET_PRODUCT_DATA, IOCTL_CHANGER_GET_PRODUCT_DATA control, IOCTL_CHANGER_GET_PRODUCT_DATA control code [Storage Devices], k307_a03cd330-a457-4f88-b1e7-2a03ff7651e8.xml, ntddchgr/IOCTL_CHANGER_GET_PRODUCT_DATA, storage.ioctl_changer_get_product_data
f1_keywords:
 - "ntddchgr/IOCTL_CHANGER_GET_PRODUCT_DATA"
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddchgr.h
api_name:
- IOCTL_CHANGER_GET_PRODUCT_DATA
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CHANGER_GET_PRODUCT_DATA IOCTL


## -description



Returns product data for the device.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_product_data">CHANGER_PRODUCT_DATA</a> data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(CHANGER_PRODUCT_DATA).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_product_data">CHANGER_PRODUCT_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetproductdata">ChangerGetProductData</a>
 

 

