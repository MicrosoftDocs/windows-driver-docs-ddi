---
UID: NI:ntddchgr.IOCTL_CHANGER_GET_PRODUCT_DATA
title: IOCTL_CHANGER_GET_PRODUCT_DATA
author: windows-driver-content
description: Returns product data for the device.
old-location: storage\ioctl_changer_get_product_data.htm
old-project: storage
ms.assetid: 2e3d0dbd-7d55-4241-9aea-f3474ab49025
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_CHANGER_GET_PRODUCT_DATA, IOCTL_CHANGER_GET_PRODUCT_DATA control code [Storage Devices], k307_a03cd330-a457-4f88-b1e7-2a03ff7651e8.xml, ntddchgr/IOCTL_CHANGER_GET_PRODUCT_DATA, storage.ioctl_changer_get_product_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddchgr.h
api_name:
-	IOCTL_CHANGER_GET_PRODUCT_DATA
product: Windows
targetos: Windows
req.typenames: ELEMENT_TYPE, *PELEMENT_TYPE
---

# IOCTL_CHANGER_GET_PRODUCT_DATA IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Returns product data for the device.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="..\ntddchgr\ns-ntddchgr-_changer_product_data.md">CHANGER_PRODUCT_DATA</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(CHANGER_PRODUCT_DATA).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH. 


## -see-also

<a href="..\mcd\nf-mcd-changergetproductdata.md">ChangerGetProductData</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_product_data.md">CHANGER_PRODUCT_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CHANGER_GET_PRODUCT_DATA control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

