---
UID: NC:ndis.NDIS_SWITCH_DEREFERENCE_SWITCH_NIC
title: NDIS_SWITCH_DEREFERENCE_SWITCH_NIC
author: windows-driver-content
description: The DereferenceSwitchNic function decrements the Hyper-V extensible switch reference counter for a network adapter that is connected to an extensible switch port. The reference counter was incremented through a previous call to ReferenceSwitchNic.
old-location: netvista\DereferenceSwitchNic.htm
old-project: netvista
ms.assetid: 58C72F81-07B9-45FE-A8BA-0405DBE4CA20
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DereferenceSwitchNic
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_SWITCH_DEREFERENCE_SWITCH_NIC callback



## -description

The <i>DereferenceSwitchNic</i> function decrements the Hyper-V extensible switch reference counter for a network adapter that is connected to an extensible switch port. The reference counter was incremented through a previous call to <a href="https://msdn.microsoft.com/8F4C76FA-A386-4A3D-8C9F-3CFF69382702">ReferenceSwitchNic</a>.



The <i>DereferenceSwitchNic</i> function decrements the Hyper-V extensible switch reference counter for a network adapter that is connected to an extensible switch port. The reference counter was incremented through a previous call to <a href="https://msdn.microsoft.com/8F4C76FA-A386-4A3D-8C9F-3CFF69382702">ReferenceSwitchNic</a>.



## -prototype

````
NDIS_SWITCH_DEREFERENCE_SWITCH_NIC DereferenceSwitchNic;

NDIS_STATUS DereferenceSwitchNic(
  _In_ NDIS_SWITCH_CONTEXT   NdisSwitchContext,
  _In_ NDIS_SWITCH_PORT_ID   SwitchPortId,
  _In_ NDIS_SWITCH_NIC_INDEX SwitchNicIndex
)
{ ... }
````


## -parameters

### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param SwitchPortId [in]

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port  to which the virtual network adapter is connected.


### -param SwitchNicIndex [in]

An NDIS_SWITCH_NIC_INDEX value that specifies the index of the virtual network adapter for which the extensible switch reference counter is to be incremented.

For more information on NDIS_SWITCH_NIC_INDEX values, see <a href="https://msdn.microsoft.com/969333DA-0282-474B-8D56-72CD623C5329">Network Adapter Index Values</a>.


## -returns
If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.




## -remarks
The extensible switch extension calls <i>DereferenceSwitchNic</i> to decrement the reference counter for a network adapter that is connected to an extensible switch port. While the extensible switch reference counter has a nonzero value, the protocol edge of the extensible switch will not issue an object identifier (OID) set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598264">OID_SWITCH_NIC_DELETE</a> to delete the connection to the adapter. 

The extension must call <i>DereferenceSwitchNic</i> if it had previously called <a href="https://msdn.microsoft.com/8F4C76FA-A386-4A3D-8C9F-3CFF69382702">ReferenceSwitchNic</a> for a network adapter connection. 


## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/8F4C76FA-A386-4A3D-8C9F-3CFF69382702">ReferenceSwitchNic</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598264">OID_SWITCH_NIC_DELETE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_DEREFERENCE_SWITCH_NIC callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

