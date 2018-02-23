---
UID: NS:ntddmmc._FEATURE_DATA_VENDOR_SPECIFIC
title: "_FEATURE_DATA_VENDOR_SPECIFIC"
author: windows-driver-content
description: The FEATURE_DATA_VENDOR_SPECIFIC structure holds information about a vendor-specific feature.
old-location: storage\feature_data_vendor_specific.htm
old-project: storage
ms.assetid: 151e6456-4c1f-453b-9eb6-a139e0f93d6e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: structs-CD-ROM_976446aa-d4d1-468b-a617-901d612b1a7e.xml, PFEATURE_DATA_VENDOR_SPECIFIC, ntddmmc/FEATURE_DATA_VENDOR_SPECIFIC, _FEATURE_DATA_VENDOR_SPECIFIC, PFEATURE_DATA_VENDOR_SPECIFIC structure pointer [Storage Devices], *PFEATURE_DATA_VENDOR_SPECIFIC, FEATURE_DATA_VENDOR_SPECIFIC structure [Storage Devices], storage.feature_data_vendor_specific, FEATURE_DATA_VENDOR_SPECIFIC, ntddmmc/PFEATURE_DATA_VENDOR_SPECIFIC
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddmmc.h
apiname:
-	FEATURE_DATA_VENDOR_SPECIFIC
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_VENDOR_SPECIFIC, *PFEATURE_DATA_VENDOR_SPECIFIC
---

# _FEATURE_DATA_VENDOR_SPECIFIC structure


## -description


The FEATURE_DATA_VENDOR_SPECIFIC structure holds information about a vendor-specific feature.


## -syntax


````
typedef struct _FEATURE_DATA_VENDOR_SPECIFIC {
  FEATURE_HEADER Header;
  UCHAR          VendorSpecificData[];
} FEATURE_DATA_VENDOR_SPECIFIC, *PFEATURE_DATA_VENDOR_SPECIFIC;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field VendorSpecificData

Contains an array that describes a vendor-specific feature. 


## -remarks



You can use this structure to access the data of any feature structure as though it were a simple character array. 




## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_VENDOR_SPECIFIC structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

