---
UID: NS:hidpddi._HIDP_DEVICE_DESC
title: "_HIDP_DEVICE_DESC"
author: windows-driver-content
description: Contains the device description block filled in collection descriptions as linked lists. This structure is used by HidP_GetCollectionDescription.
old-location: hid\hidp_device_desc.htm
old-project: hid
ms.assetid: C51D645B-5DF2-4F23-904B-AB56F97520CB
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PHIDP_DEVICE_DESC, HIDP_DEVICE_DESC, HIDP_DEVICE_DESC structure [Human Input Devices], PHIDP_DEVICE_DESC, PHIDP_DEVICE_DESC structure pointer [Human Input Devices], _HIDP_DEVICE_DESC, hid.hidp_device_desc, hidpddi/HIDP_DEVICE_DESC, hidpddi/PHIDP_DEVICE_DESC"
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
-	HIDP_DEVICE_DESC
product:
- Windows
targetos: Windows
req.typenames: HIDP_DEVICE_DESC, *PHIDP_DEVICE_DESC
---

# _HIDP_DEVICE_DESC structure


## -description


Contains the device description block filled in
                         collection descriptions as linked lists. This structure is used by <a href="https://msdn.microsoft.com/library/windows/hardware/mt740164">HidP_GetCollectionDescription</a>.


## -struct-fields




### -field CollectionDesc

An array of  <a href="https://msdn.microsoft.com/library/windows/hardware/mt740161">HIDP_COLLECTION_DESC</a> structure that contains the collection descriptors.


### -field CollectionDescLength

The number of elements in the array of the collection descriptors.


### -field ReportIDs

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/mt740165">HIDP_REPORT_IDS</a> structures report ID information for a report descriptor. 


### -field ReportIDsLength

The number of elements in the length of the array of report IDs.


### -field Dbg

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt740163">HIDP_GETCOLDESC_DBG</a> structure that contains the error code indicating the failure in parsing the report 
                                      descriptor.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt740164">HidP_GetCollectionDescription</a>
 

 

