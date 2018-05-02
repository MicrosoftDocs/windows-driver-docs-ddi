---
UID: NE:ntddk._BDCB_CLASSIFICATION
title: "_BDCB_CLASSIFICATION"
author: windows-driver-content
description: The BDCB_CLASSIFICATION enumeration lists different classifications of boot start images.
old-location: kernel\bdcb_classification.htm
old-project: kernel
ms.assetid: 01627E7A-460F-4E49-B98C-0FCCFAB2F8BB
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PBDCB_CLASSIFICATION, BDCB_CLASSIFICATION, BDCB_CLASSIFICATION enumeration [Kernel-Mode Driver Architecture], BdCbClassificationEnd, BdCbClassificationKnownBadImage, BdCbClassificationKnownBadImageBootCritical, BdCbClassificationKnownGoodImage, BdCbClassificationUnknownImage, _BDCB_CLASSIFICATION, kernel.bdcb_classification, ntddk/BDCB_CLASSIFICATION, ntddk/BdCbClassificationEnd, ntddk/BdCbClassificationKnownBadImage, ntddk/BdCbClassificationKnownBadImageBootCritical, ntddk/BdCbClassificationKnownGoodImage, ntddk/BdCbClassificationUnknownImage"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	BDCB_CLASSIFICATION
product: Windows
targetos: Windows
req.typenames: BDCB_CLASSIFICATION, *PBDCB_CLASSIFICATION
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




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406359">BDCB_IMAGE_INFORMATION</a>



<a href="https://msdn.microsoft.com/28BA4B54-F493-4D79-89DF-D890EBCF1E9C">BOOT_DRIVER_CALLBACK_FUNCTION</a>
 

 

