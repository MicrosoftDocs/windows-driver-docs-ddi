---
UID: NF:rxce.RxCeFreeIrp
title: RxCeFreeIrp function (rxce.h)
description: RxCeFreeIrp frees an IRP.
old-location: ifsk\rxcefreeirp.htm
tech.root: ifsk
ms.assetid: 71e3283c-2dbc-4579-a374-e51e123b852f
ms.date: 04/16/2018
ms.keywords: RxCeFreeIrp, RxCeFreeIrp function [Installable File System Drivers], ifsk.rxcefreeirp, rxce/RxCeFreeIrp, rxref_93b8da8d-d9fe-41e3-8423-5b3d8102f7a7.xml
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h
req.target-type: Desktop
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxce.h
api_name:
- RxCeFreeIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxCeFreeIrp function


## -description


<b>RxCeFreeIrp</b> frees an IRP.


## -parameters




### -param pIrp

A pointer to the IRP to be freed.


## -returns



None 




## -remarks



An IRP allocated with an associated memory descriptor list allocated with <b>RxCeAllocateIrpWithMDL</b> should be freed when the IRP is completed using <b>RxCeFreeIrp</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_mdl">MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/rxce/nf-rxce-rxceallocateirpwithmdl">RxCeAllocateIrpWithMDL</a>
 

 

