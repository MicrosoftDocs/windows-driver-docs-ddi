---
UID: NE:filterpipeline.__MIDL___MIDL_itf_filterpipeline_0000_0000_0003
title: __MIDL___MIDL_itf_filterpipeline_0000_0000_0003 (filterpipeline.h)
description: The EXpsJobConsumption enumeration describes job consumption updates.
old-location: print\expsjobconsumption.htm
tech.root: print
ms.assetid: 9fab1cba-fe67-4654-ae33-3de41f0427f7
ms.date: 04/20/2018
ms.keywords: EXpsJobConsumption, EXpsJobConsumption enumeration [Print Devices], XpsJob_DocumentSequenceAdded, XpsJob_FixedDocumentAdded, XpsJob_FixedPageAdded, __MIDL___MIDL_itf_filterpipeline_0000_0000_0003, filterpipeline/EXpsJobConsumption, filterpipeline/XpsJob_DocumentSequenceAdded, filterpipeline/XpsJob_FixedDocumentAdded, filterpipeline/XpsJob_FixedPageAdded, filterpipeline_67998379-96d5-4e6f-abc3-602526b12276.xml, print.expsjobconsumption
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- filterpipeline.h
api_name:
- EXpsJobConsumption
product:
- Windows
targetos: Windows
req.typenames: EXpsJobConsumption
---

# __MIDL___MIDL_itf_filterpipeline_0000_0000_0003 enumeration


## -description


The EXpsJobConsumption enumeration describes job consumption updates.


## -enum-fields




### -field XpsJob_DocumentSequenceAdded

A document sequence is added to the job.


### -field XpsJob_FixedDocumentAdded

A fixed document is added to the job.


### -field XpsJob_FixedPageAdded

A fixed page is added to the job.


## -remarks



A rendering filter uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554314">IPrintPipelineProgressReport</a> interface to send updates to the pipeline. 

Rendering filters convert XPS to the page description language (PDL). 

A pipeline does not necessarily need one of the EXpsJobConsumption enumeration values.



