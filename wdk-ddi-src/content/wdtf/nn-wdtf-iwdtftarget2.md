---
UID: NN:wdtf.IWDTFTarget2
title: IWDTFTarget2 (wdtf.h)
description: Defines operations and properties for a testable item.
old-location: dtf\iwdtftarget2.htm
tech.root: dtf
ms.assetid: fc75c201-a3ff-44f7-ba09-8e3554b1cf27
ms.date: 04/04/2018
ms.keywords: IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], IWDTFTarget2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFTarget2, dtf.iwdtftarget2, wdtf/IWDTFTarget2
ms.topic: interface
f1_keywords:
 - "wdtf/IWDTFTarget2"
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
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
- WDTF.Interop.metadata_dll.dll
api_name:
- IWDTFTarget2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTarget2 interface


## -description


Defines operations and properties for a testable item.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFTarget2</b> interface inherits from <b>ITracing</b>. <b>IWDTFTarget2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -remarks



The <b>IWDTFTarget2</b> interface abstracts the notion of a testable item, 
which is the central focus of the WDTF object model.
You can retrieve instances of the <b>IWDTFTarget2</b> interface only 
through other interfaces (such as the 
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtfdevicedepot2">IWDTFDeviceDepot2</a> interface or
the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtfsystemdepot2">IWDTFSystemDepot2</a> interface). 

The lifetime of a target is tied to its creator; that is, if you retrieve a target 
from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtf2-get_devicedepot">DeviceDepot</a> property, 
the target will exist as long as the <b>DeviceDepot</b> 
property exists.

You cannot copy an instance of the <b>IWDTFTarget2</b> interface. 
Even if you add a target to a collection, you really just add a reference to the same instance.

<b>Implementation Details</b>

ProgID: (Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">IWDTF</a> 
aggregation interface to instantiate)

TraceLevel Path: HKCR\WDTF.Target.1\

<div class="alert"><b>Note</b>  The implementation of this interface is not thread-safe.</div>
<div> </div>


