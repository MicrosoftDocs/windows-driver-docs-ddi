---
UID: NS:ntddchgr._CHANGER_PRODUCT_DATA
title: "_CHANGER_PRODUCT_DATA"
author: windows-driver-content
description: The CHANGER_PRODUCT_DATA structure is used in conjunction with the IOCTL_CHANGER_GET_PRODUCT_DATA request to retrieve product data for a device.
old-location: storage\changer_product_data.htm
old-project: storage
ms.assetid: 18e5b394-b0ea-481c-b634-83a2ebec4784
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCHANGER_PRODUCT_DATA, CHANGER_PRODUCT_DATA, CHANGER_PRODUCT_DATA structure [Storage Devices], PCHANGER_PRODUCT_DATA, PCHANGER_PRODUCT_DATA structure pointer [Storage Devices], _CHANGER_PRODUCT_DATA, ntddchgr/CHANGER_PRODUCT_DATA, ntddchgr/PCHANGER_PRODUCT_DATA, storage.changer_product_data, structs-changer_10598085-7fbc-40f9-a04c-ca8973faace7.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddchgr.h
req.include-header: 
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
-	ntddchgr.h
api_name:
-	CHANGER_PRODUCT_DATA
product: Windows
targetos: Windows
req.typenames: CHANGER_PRODUCT_DATA, *PCHANGER_PRODUCT_DATA
---

# _CHANGER_PRODUCT_DATA structure


## -description


The CHANGER_PRODUCT_DATA structure is used in conjunction with the <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_product_data.md">IOCTL_CHANGER_GET_PRODUCT_DATA</a> request to retrieve product data for a device. 


## -syntax


````
typedef struct _CHANGER_PRODUCT_DATA {
  UCHAR VendorId[VENDOR_ID_LENGTH];
  UCHAR ProductId[PRODUCT_ID_LENGTH];
  UCHAR Revision[REVISION_LENGTH];
  UCHAR SerialNumber[SERIAL_NUMBER_LENGTH];
  UCHAR DeviceType;
} CHANGER_PRODUCT_DATA, *PCHANGER_PRODUCT_DATA;
````


## -struct-fields




### -field VendorId

Specifies the name of the device manufacturer. 


### -field ProductId

Specifies the product identification as defined by the vendor.


### -field Revision

Specifies the product revision as defined by the vendor.


### -field SerialNumber

Specifies the value defined by the vendor to identify this device. Serial numbers are unique for all changers of a given type, but are not necessarily unique across vendor and product lines. For a SCSI changer, this value might be from Vital Product Data. If <b>SerialNumber</b> is not unique, the miniclass driver should not set the CHANGER_SERIAL_NUMBER_VALID flag in the <b>Features0</b> member of the <a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a> structure. 


### -field DeviceType

Specifies the device type of the changer. This member must be MEDIUM_CHANGER.


## -see-also

<a href="..\mcd\nf-mcd-changergetproductdata.md">ChangerGetProductData</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_product_data.md">IOCTL_CHANGER_GET_PRODUCT_DATA</a>



<a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>



 

 


