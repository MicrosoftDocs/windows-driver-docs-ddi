---
UID: NE:filterpipeline.__MIDL___MIDL_itf_filterpipeline_0000_0000_0003
title: "__MIDL___MIDL_itf_filterpipeline_0000_0000_0003"
author: windows-driver-content
description: The EXpsJobConsumption enumeration describes job consumption updates.
old-location: print\expsjobconsumption.htm
old-project: print
ms.assetid: 9fab1cba-fe67-4654-ae33-3de41f0427f7
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: XpsJob_DocumentSequenceAdded, __MIDL___MIDL_itf_filterpipeline_0000_0000_0003, filterpipeline/XpsJob_DocumentSequenceAdded, filterpipeline/XpsJob_FixedDocumentAdded, filterpipeline/XpsJob_FixedPageAdded, EXpsJobConsumption enumeration [Print Devices], XpsJob_FixedPageAdded, filterpipeline_67998379-96d5-4e6f-abc3-602526b12276.xml, EXpsJobConsumption, XpsJob_FixedDocumentAdded, print.expsjobconsumption, filterpipeline/EXpsJobConsumption
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	filterpipeline.h
apiname:
-	EXpsJobConsumption
product: Windows
targetos: Windows
req.typenames: EXpsJobConsumption
---

# __MIDL___MIDL_itf_filterpipeline_0000_0000_0003 enumeration


## -description


The EXpsJobConsumption enumeration describes job consumption updates.


## -syntax


````
typedef enum  { 
  XpsJob_DocumentSequenceAdded,
  XpsJob_FixedDocumentAdded,
  XpsJob_FixedPageAdded
} EXpsJobConsumption;
````


## -enum-fields




### -field XpsJob_DocumentSequenceAdded

A document sequence is added to the job.


### -field XpsJob_FixedDocumentAdded

A fixed document is added to the job.


### -field XpsJob_FixedPageAdded

A fixed page is added to the job.


## -remarks



A rendering filter uses the <a href="..\filterpipeline\nn-filterpipeline-iprintpipelineprogressreport.md">IPrintPipelineProgressReport</a> interface to send updates to the pipeline. 

Rendering filters convert XPS to the page description language (PDL). 

A pipeline does not necessarily need one of the EXpsJobConsumption enumeration values.



