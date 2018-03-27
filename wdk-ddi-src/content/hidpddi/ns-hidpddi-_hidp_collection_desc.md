---
UID: NS:hidpddi._HIDP_COLLECTION_DESC
title: "_HIDP_COLLECTION_DESC"
author: windows-driver-content
description: Contains the information of a top-level-collection. This structure is used in the HidP_GetCollectionDescription call.
old-location: hid\hidp_collection_desc.htm
old-project: hid
ms.assetid: 4B044635-1088-4CED-87C7-4385E565A54A
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PHIDP_COLLECTION_DESC, HIDP_COLLECTION_DESC, HIDP_COLLECTION_DESC structure [Human Input Devices], PHIDP_COLLECTION_DESC, PHIDP_COLLECTION_DESC structure pointer [Human Input Devices], _HIDP_COLLECTION_DESC, hid.hidp_collection_desc, hidpddi/HIDP_COLLECTION_DESC, hidpddi/PHIDP_COLLECTION_DESC"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidpddi.h
req.include-header: Hidpddi.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Hidpddi.h
api_name:
-	HIDP_COLLECTION_DESC
product: Windows
targetos: Windows
req.typenames: HIDP_COLLECTION_DESC, *PHIDP_COLLECTION_DESC
---

# _HIDP_COLLECTION_DESC structure


## -description


Contains the information of a top-level-collection. This structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt740164">HidP_GetCollectionDescription</a> call.


## -struct-fields




### -field UsagePage

Specifies the usage page of the usage ID specified by <b>Usage</b>.


### -field Usage

Indicates a usage ID.


### -field CollectionNumber

The index of the collection in the array of  <b>HIDP_COLLECTION_DESC</b> structure. This is a 1-based value.


### -field Reserved

Reserved for internal system use. Must be 0.


### -field InputLength

The maximum length of an input report of this collection.


### -field OutputLength

The maximum length of an output report of this collection.


### -field FeatureLength

The maximum length of a feature report of this collection.


### -field PreparsedDataLength

The length of the preparsed data pointed to by <i>PreparsedData</i>.


### -field PreparsedData

A pointer to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a> structure that contains a top-level collection's preparsed data.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt740164">HidP_GetCollectionDescription</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HIDP_COLLECTION_DESC structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

