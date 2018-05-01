---
UID: NF:ks.KsFilterAddTopologyConnections
title: KsFilterAddTopologyConnections function
author: windows-driver-content
description: The KsFilterAddTopologyConnections function adds new topology connections to a filter.
old-location: stream\ksfilteraddtopologyconnections.htm
old-project: stream
ms.assetid: 32a61103-5f2f-4b73-a299-bf6a14c3bec9
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsFilterAddTopologyConnections, KsFilterAddTopologyConnections function [Streaming Media Devices], avfunc_99b8984f-5ca2-460b-ab20-230fd09b6d13.xml, ks/KsFilterAddTopologyConnections, stream.ksfilteraddtopologyconnections
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsFilterAddTopologyConnections
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterAddTopologyConnections function


## -description


The<b> KsFilterAddTopologyConnections</b> function adds new topology connections to a filter.


## -parameters




### -param Filter [in]

<i>A pointer</i> to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> to which to add the new connections.


### -param NewConnectionsCount [in]

The number of connections in <i>NewTopologyConnections</i>.


### -param NewTopologyConnections [in]

A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff567148">KSTOPOLOGY_CONNECTION</a> structures containing the new topology connections.


## -returns



<b>KsFilterAddTopologyConnections </b>returns STATUS_SUCCESS or an error code indicating failure of the attempt to add topology connections.




## -remarks



Note that the filter control mutex must be held before calling this function.

For more information about mutexes, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567148">KSTOPOLOGY_CONNECTION</a>
 

 

