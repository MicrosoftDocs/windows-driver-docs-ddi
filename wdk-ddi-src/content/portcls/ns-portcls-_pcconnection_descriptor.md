---
UID: NS:portcls._PCCONNECTION_DESCRIPTOR
title: _PCCONNECTION_DESCRIPTOR (portcls.h)
description: The PCCONNECTION_DESCRIPTOR structure describes a single data-path connection inside a KS filter. 
old-location: audio\PCCONNECTION_DESCRIPTOR.htm
tech.root: audio
ms.assetid: EEE091E4-29D1-4C6F-B543-C54736660CCA
ms.date: 05/08/2018
keywords: ["PCCONNECTION_DESCRIPTOR structure"]
ms.keywords: "*PPCCONNECTION_DESCRIPTOR, PCCONNECTION_DESCRIPTOR, PCCONNECTION_DESCRIPTOR structure [Audio Devices], PPCCONNECTION_DESCRIPTOR, PPCCONNECTION_DESCRIPTOR structure pointer [Audio Devices], _PCCONNECTION_DESCRIPTOR, audio.PCCONNECTION_DESCRIPTOR, portcls/PCCONNECTION_DESCRIPTOR, portcls/PPCCONNECTION_DESCRIPTOR"
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
targetos: Windows
req.typenames: PCCONNECTION_DESCRIPTOR, *PPCCONNECTION_DESCRIPTOR
f1_keywords:
 - _PCCONNECTION_DESCRIPTOR
 - portcls/_PCCONNECTION_DESCRIPTOR
 - PPCCONNECTION_DESCRIPTOR
 - portcls/PPCCONNECTION_DESCRIPTOR
 - PCCONNECTION_DESCRIPTOR
 - portcls/PCCONNECTION_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Portcls.h
api_name:
 - PCCONNECTION_DESCRIPTOR
---

# _PCCONNECTION_DESCRIPTOR structure


## -description

<p>The <strong>PCCONNECTION_DESCRIPTOR</strong> structure describes a single data-path connection inside a KS filter. A filter's internal topology can be specified by an array of <strong>PCCONNECTION_DESCRIPTOR</strong> structures. A WDM audio adapter driver returns an array of these structures in response to a <a href="https://msdn.microsoft.com/library/ff536765(v=vs.85)" data-linktype="external"><strong>IMiniport::GetDescription</strong></a> call or a <a href="https://msdn.microsoft.com/library/ff565802(v=vs.85)" data-linktype="external"><strong>KSPROPERTY_TOPOLOGY_CONNECTIONS</strong></a> get-property request. <strong>PCCONNECTION_DESCRIPTOR</strong> is an alias for <a href="https://msdn.microsoft.com/library/ff567148(v=vs.85)" data-linktype="external"><strong>KSTOPOLOGY_CONNECTION</strong></a>.</p>

## -struct-fields

### -field TBD


<h2 id="requirements">Requirements</h2>
<table>
<colgroup>
<col/>
<col/>
</colgroup>
<tbody>
<tr class="odd">
<td><p>Header</p></td>
<td>Portcls.h (include Portcls.h)</td>
</tr>
</tbody>

## -see-also

<p><a href="https://msdn.microsoft.com/library/ff536765(v=vs.85)" data-linktype="external"><strong>IMiniport::GetDescription</strong></a></p>

<p><a href="https://msdn.microsoft.com/library/ff565802(v=vs.85)" data-linktype="external"><strong>KSPROPERTY_TOPOLOGY_CONNECTIONS</strong></a></p>

<p><a href="https://msdn.microsoft.com/library/ff567148(v=vs.85)" data-linktype="external"><strong>KSTOPOLOGY_CONNECTION</strong></a></p>

<p><a href="https://msdn.microsoft.com/library/ff537695(v=vs.85)" data-linktype="external"><strong>PCFILTER_NODE</strong></a></p>

<p><a href="https://msdn.microsoft.com/library/ff537694(v=vs.85)" data-linktype="external"><strong>PCFILTER_DESCRIPTOR</strong></a></p>
