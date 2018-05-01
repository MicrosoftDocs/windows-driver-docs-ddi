---
UID: NS:ntddmmc._FEATURE_DATA_VENDOR_SPECIFIC
title: "_FEATURE_DATA_VENDOR_SPECIFIC"
author: windows-driver-content
description: The FEATURE_DATA_VENDOR_SPECIFIC structure holds information about a vendor-specific feature.
old-location: storage\feature_data_vendor_specific.htm
old-project: storage
ms.assetid: 151e6456-4c1f-453b-9eb6-a139e0f93d6e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_VENDOR_SPECIFIC, FEATURE_DATA_VENDOR_SPECIFIC, FEATURE_DATA_VENDOR_SPECIFIC structure [Storage Devices], PFEATURE_DATA_VENDOR_SPECIFIC, PFEATURE_DATA_VENDOR_SPECIFIC structure pointer [Storage Devices], _FEATURE_DATA_VENDOR_SPECIFIC, ntddmmc/FEATURE_DATA_VENDOR_SPECIFIC, ntddmmc/PFEATURE_DATA_VENDOR_SPECIFIC, storage.feature_data_vendor_specific, structs-CD-ROM_976446aa-d4d1-468b-a617-901d612b1a7e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
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
-	ntddmmc.h
api_name:
-	FEATURE_DATA_VENDOR_SPECIFIC
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_VENDOR_SPECIFIC, *PFEATURE_DATA_VENDOR_SPECIFIC
---

# _FEATURE_DATA_VENDOR_SPECIFIC structure


## -description


The FEATURE_DATA_VENDOR_SPECIFIC structure holds information about a vendor-specific feature.


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field VendorSpecificData

Contains an array that describes a vendor-specific feature. 


## -remarks



You can use this structure to access the data of any feature structure as though it were a simple character array. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

