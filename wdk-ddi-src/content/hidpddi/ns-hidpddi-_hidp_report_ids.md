---
UID: NS:hidpddi._HIDP_REPORT_IDS
title: "_HIDP_REPORT_IDS"
author: windows-driver-content
description: Contains report ID information for a top-level collection.
old-location: hid\hidp_report_ids.htm
old-project: hid
ms.assetid: C88B77C3-01CB-4E8C-83A4-EB9AFB122327
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: HIDP_REPORT_IDS structure [Human Input Devices], PHIDP_REPORT_IDS structure pointer [Human Input Devices], hidpddi/PHIDP_REPORT_IDS, _HIDP_REPORT_IDS, hidpddi/HIDP_REPORT_IDS, hid.hidp_report_ids, *PHIDP_REPORT_IDS, HIDP_REPORT_IDS, PHIDP_REPORT_IDS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Hidpddi.h
apiname:
-	HIDP_REPORT_IDS
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_IDS, *PHIDP_REPORT_IDS
---

# _HIDP_REPORT_IDS structure


## -description


Contains report ID information for a top-level collection. 


## -syntax


````
typedef struct _HIDP_REPORT_IDS {
  UCHAR               ReportID;
  UCHAR               CollectionNumber;
  USHORT              InputLength;
  USHORT              OutputLength;
  USHORT              FeatureLength;
} HIDP_REPORT_IDS, *PHIDP_REPORT_IDS;
````


## -struct-fields




### -field ReportID

The report ID of the top-level collection.


### -field CollectionNumber

The index of the collection in the array of  <a href="..\hidpddi\ns-hidpddi-_hidp_collection_desc.md">HIDP_COLLECTION_DESC</a> structure.


### -field InputLength

The length of an input report of this report ID. 


### -field OutputLength

The length of an output report of this report ID. An input report, an output report, and a feature report can use the same report.


### -field FeatureLength

The length of a feature report of this report ID.


## -see-also

<a href="..\hidpddi\nf-hidpddi-hidp_getcollectiondescription.md">HidP_GetCollectionDescription</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HIDP_REPORT_IDS structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

