---
UID: NS:ntddchgr._CHANGER_PRODUCT_DATA
title: _CHANGER_PRODUCT_DATA (ntddchgr.h)
description: The CHANGER_PRODUCT_DATA structure is used in conjunction with the IOCTL_CHANGER_GET_PRODUCT_DATA request to retrieve product data for a device.
old-location: storage\changer_product_data.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["CHANGER_PRODUCT_DATA structure"]
ms.keywords: "*PCHANGER_PRODUCT_DATA, CHANGER_PRODUCT_DATA, CHANGER_PRODUCT_DATA structure [Storage Devices], PCHANGER_PRODUCT_DATA, PCHANGER_PRODUCT_DATA structure pointer [Storage Devices], _CHANGER_PRODUCT_DATA, ntddchgr/CHANGER_PRODUCT_DATA, ntddchgr/PCHANGER_PRODUCT_DATA, storage.changer_product_data, structs-changer_10598085-7fbc-40f9-a04c-ca8973faace7.xml"
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
targetos: Windows
req.typenames: CHANGER_PRODUCT_DATA, *PCHANGER_PRODUCT_DATA
f1_keywords:
 - _CHANGER_PRODUCT_DATA
 - ntddchgr/_CHANGER_PRODUCT_DATA
 - PCHANGER_PRODUCT_DATA
 - ntddchgr/PCHANGER_PRODUCT_DATA
 - CHANGER_PRODUCT_DATA
 - ntddchgr/CHANGER_PRODUCT_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddchgr.h
api_name:
 - _CHANGER_PRODUCT_DATA
 - PCHANGER_PRODUCT_DATA
 - CHANGER_PRODUCT_DATA
---

# _CHANGER_PRODUCT_DATA structure


## -description

The CHANGER_PRODUCT_DATA structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_product_data">IOCTL_CHANGER_GET_PRODUCT_DATA</a> request to retrieve product data for a device.

## -struct-fields

### -field VendorId

Specifies the name of the device manufacturer.

### -field ProductId

Specifies the product identification as defined by the vendor.

### -field Revision

Specifies the product revision as defined by the vendor.

### -field SerialNumber

Specifies the value defined by the vendor to identify this device. Serial numbers are unique for all changers of a given type, but are not necessarily unique across vendor and product lines. For a SCSI changer, this value might be from Vital Product Data. If <b>SerialNumber</b> is not unique, the miniclass driver should not set the CHANGER_SERIAL_NUMBER_VALID flag in the <b>Features0</b> member of the <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a> structure.

### -field DeviceType

Specifies the device type of the changer. This member must be MEDIUM_CHANGER.

## -see-also

<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetproductdata">ChangerGetProductData</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_product_data">IOCTL_CHANGER_GET_PRODUCT_DATA</a>

