---
UID: NN:printerextension.IPrintJobCollection
title: IPrintJobCollection (printerextension.h)
description: This interfaces provides an enumeration of the jobs in the print queue.
old-location: print\iprintjobcollection.htm
tech.root: print
ms.assetid: 757328A6-DD2C-4057-820B-39EB83277194
ms.date: 04/20/2018
keywords: ["IPrintJobCollection interface"]
ms.keywords: IPrintJobCollection, IPrintJobCollection interface [Print Devices], IPrintJobCollection interface [Print Devices],described, print.iprintjobcollection, printerextension/IPrintJobCollection
f1_keywords:
 - "printerextension/IPrintJobCollection"
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrintJobCollection
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintJobCollection interface


## -description


This interfaces provides an enumeration of the jobs in the print queue.

The enumerated list of jobs represents a snapshot of the current job status.


## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IPrintJobCollection</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintJobCollection</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -remarks



The order of print jobs in the enumerated list is the same as the order provided by <a href="https://docs.microsoft.com/windows/desktop/printdocs/enumjobs">EnumJobs</a>, which is the actual print queue order.

<b>IPrintJobCollection</b> also helps to make it possible to perform job management from a UWP device app or from a printer extension. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/job-management">Job Management</a>.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/printdocs/enumjobs">EnumJobs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/job-management">Job Management</a>
 

 

