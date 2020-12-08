---
UID: NF:ks.KsFilterAddTopologyConnections
title: KsFilterAddTopologyConnections function (ks.h)
description: The KsFilterAddTopologyConnections function adds new topology connections to a filter.
old-location: stream\ksfilteraddtopologyconnections.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsFilterAddTopologyConnections function"]
ms.keywords: KsFilterAddTopologyConnections, KsFilterAddTopologyConnections function [Streaming Media Devices], avfunc_99b8984f-5ca2-460b-ab20-230fd09b6d13.xml, ks/KsFilterAddTopologyConnections, stream.ksfilteraddtopologyconnections
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsFilterAddTopologyConnections
 - ks/KsFilterAddTopologyConnections
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsFilterAddTopologyConnections
---

# KsFilterAddTopologyConnections function


## -description

The<b> KsFilterAddTopologyConnections</b> function adds new topology connections to a filter.

## -parameters

### -param Filter 

[in]
<i>A pointer</i> to the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> to which to add the new connections.

### -param NewConnectionsCount 

[in]
The number of connections in <i>NewTopologyConnections</i>.

### -param NewTopologyConnections 

[in]
A pointer to an array of <a href="/windows-hardware/drivers/ddi/ks/ns-ks-kstopology_connection">KSTOPOLOGY_CONNECTION</a> structures containing the new topology connections.

## -returns

<b>KsFilterAddTopologyConnections </b>returns STATUS_SUCCESS or an error code indicating failure of the attempt to add topology connections.

## -remarks

Note that the filter control mutex must be held before calling this function.

For more information about mutexes, see <a href="/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-kstopology_connection">KSTOPOLOGY_CONNECTION</a>
