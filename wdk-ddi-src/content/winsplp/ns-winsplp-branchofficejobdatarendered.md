---
UID: NS:winsplp.BranchOfficeJobDataRendered
title: BranchOfficeJobDataRendered
author: windows-driver-content
description: Contains the necessary data for logging a branch office job Pipeline Rendering Event on a remote server. This is based on job-related data available to the spooler.
old-location: print\branchofficejobdatarendered.htm
old-project: print
ms.assetid: 67A296B3-5D59-475E-9026-EDAB90C8E3DD
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PBranchOfficeJobDataRendered, BranchOfficeJobDataRendered, print.branchofficejobdatarendered, PBranchOfficeJobDataRendered, PBranchOfficeJobDataRendered structure pointer [Print Devices], winsplp/BranchOfficeJobDataRendered, winsplp/PBranchOfficeJobDataRendered, BranchOfficeJobDataRendered structure [Print Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Winsplp.h
apiname:
-	BranchOfficeJobDataRendered
product: Windows
targetos: Windows
req.typenames: "*PBranchOfficeJobDataRendered, BranchOfficeJobDataRendered"
req.product: Windows 10 or later.
---

# BranchOfficeJobDataRendered structure


## -description


Contains the necessary data for logging a branch office job Pipeline Rendering Event on a remote server. This is based on job-related data available to the spooler.


## -syntax


````
typedef struct {
  LONGLONG Size;
  DWORD    ICMMethod;
  short    Color;
  short    PrintQuality;
  short    YResolution;
  short    Copies;
  short    TTOption;
} BranchOfficeJobDataRendered, *PBranchOfficeJobDataRendered;
````


## -struct-fields




#### - Size

Specifies the 64-bit size of the job.


#### - ICMMethod

Describes the <b>DWORD</b> type member <b>ICMMethod</b>.


#### - Color

Describes the <b>short</b> type member <b>Color</b>.


#### - PrintQuality

Describes the <b>short</b> type member <b>PrintQuality</b>.


#### - YResolution

Describes the <b>short</b> type member <b>YResolution</b>.


#### - Copies

Describes the <b>short</b> type member <b>Copies</b>.


#### - TTOption

Describes the <b>short</b> type member <b>TTOption</b>.

