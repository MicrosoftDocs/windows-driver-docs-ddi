---
UID: NE:ntddk._BDCB_CLASSIFICATION
title: _BDCB_CLASSIFICATION (ntddk.h)
description: The BDCB_CLASSIFICATION enumeration lists different classifications of boot start images.
old-location: kernel\bdcb_classification.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["BDCB_CLASSIFICATION enumeration"]
ms.keywords: "*PBDCB_CLASSIFICATION, BDCB_CLASSIFICATION, BDCB_CLASSIFICATION enumeration [Kernel-Mode Driver Architecture], BdCbClassificationEnd, BdCbClassificationKnownBadImage, BdCbClassificationKnownBadImageBootCritical, BdCbClassificationKnownGoodImage, BdCbClassificationUnknownImage, _BDCB_CLASSIFICATION, kernel.bdcb_classification, ntddk/BDCB_CLASSIFICATION, ntddk/BdCbClassificationEnd, ntddk/BdCbClassificationKnownBadImage, ntddk/BdCbClassificationKnownBadImageBootCritical, ntddk/BdCbClassificationKnownGoodImage, ntddk/BdCbClassificationUnknownImage"
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
req.typenames: BDCB_CLASSIFICATION, *PBDCB_CLASSIFICATION
f1_keywords:
 - _BDCB_CLASSIFICATION
 - ntddk/_BDCB_CLASSIFICATION
 - PBDCB_CLASSIFICATION
 - ntddk/PBDCB_CLASSIFICATION
 - BDCB_CLASSIFICATION
 - ntddk/BDCB_CLASSIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _BDCB_CLASSIFICATION
 - PBDCB_CLASSIFICATION
 - BDCB_CLASSIFICATION
---

# _BDCB_CLASSIFICATION enumeration


## -description

The BDCB_CLASSIFICATION enumeration lists different classifications of boot start images.

## -enum-fields

### -field BdCbClassificationUnknownImage

The boot start image has not been inspected by anti-malware or anti-malware does not have enough information to determine whether the binary is malware.

### -field BdCbClassificationKnownGoodImage

The boot start image has been inspected by anti-malware and found not to be malware.

### -field BdCbClassificationKnownBadImage

The boot start image has been inspected by anti-malware and found to be malware.

### -field BdCbClassificationKnownBadImageBootCritical

The boot start image has been inspected by anti-malware and found to be malware, but the anti-malware boot-start driver also knows it to be critical to the success of the boot.

### -field BdCbClassificationEnd

Do not use. Reserved for future use.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_bdcb_image_information">BDCB_IMAGE_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioregisterbootdrivercallback">BOOT_DRIVER_CALLBACK_FUNCTION</a>

