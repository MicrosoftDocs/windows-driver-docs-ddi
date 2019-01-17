---
UID: NF:ks.KsTopologyPropertyHandler
title: KsTopologyPropertyHandler function
description: The KsTopologyPropertyHandler function performs standard handling of the static members of the KSPROPSETID_Topology Property Set. The function uses the KSTOPOLOGY structure, which describes the set of information that is returned by this property set.
old-location: stream\kstopologypropertyhandler.htm
tech.root: stream
ms.assetid: fe033614-b1a0-490b-b45b-a8d8de650dbf
ms.date: 04/23/2018
ms.keywords: KsTopologyPropertyHandler, KsTopologyPropertyHandler function [Streaming Media Devices], ks/KsTopologyPropertyHandler, ksfunc_d007eab3-23b3-42ea-a1d9-b2be806cb4ea.xml, stream.kstopologypropertyhandler
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsTopologyPropertyHandler
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsTopologyPropertyHandler function


## -description


The <b>KsTopologyPropertyHandler</b> function performs standard handling of the static members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566598">KSPROPSETID_Topology</a> Property Set. The function uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567146">KSTOPOLOGY</a> structure, which describes the set of information that is returned by this property set.


## -parameters




### -param Irp [in]

Specifies the IRP handling the property request.


### -param Property [in]

Specifies the specific property being queried.


### -param Data [in, out]

Specifies the topology property-specific data.


### -param Topology [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567146">KSTOPOLOGY</a> structure containing the topology information.


## -returns



The <b>KsTopologyPropertyHandler</b> function returns STATUS_SUCCESS if successful, or it returns an error specific to the property being handled. The function always fills in the IO_STATUS_BLOCK.Information field of the PIRP.IoStatus element within the IRP. It does not set the IO_STATUS_BLOCK.Status field, nor does it complete the IRP. 



