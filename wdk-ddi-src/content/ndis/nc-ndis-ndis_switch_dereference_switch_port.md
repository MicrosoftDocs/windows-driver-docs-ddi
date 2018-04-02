---
UID: NC:ndis.NDIS_SWITCH_DEREFERENCE_SWITCH_PORT
title: NDIS_SWITCH_DEREFERENCE_SWITCH_PORT
author: windows-driver-content
description: The DereferenceSwitchPort function decrements the Hyper-V extensible switch reference counter for an extensible switch port. The reference counter was incremented through a previous call to ReferenceSwitchPort.
old-location: netvista\DereferenceSwitchPort.htm
old-project: netvista
ms.assetid: 976D3A69-C539-4C8E-9664-F85717E5F712
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: DereferenceSwitchPort, DereferenceSwitchPort callback function [Network Drivers Starting with Windows Vista], NDIS_SWITCH_DEREFERENCE_SWITCH_PORT, ndis/DereferenceSwitchPort, netvista.DereferenceSwitchPort
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	DereferenceSwitchPort
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_SWITCH_DEREFERENCE_SWITCH_PORT callback


## -description



The <i>DereferenceSwitchPort</i> function decrements the Hyper-V extensible switch reference counter for an extensible switch port. The reference counter was incremented through a previous call to <a href="https://msdn.microsoft.com/5FD2E931-AC9F-4157-9C45-F93261FC834D">ReferenceSwitchPort</a>.




## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh598204">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param SwitchPortId [in]

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port for which the extensible switch reference counter is incremented.


## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The extensible switch extension calls <i>DereferenceSwitchPort</i> to decrement the reference counter for an extensible switch port. While the extensible switch reference counter has a nonzero value, the protocol edge of the extensible switch will not issue an object identifier (OID) set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598273">OID_SWITCH_PORT_DELETE</a> to delete the port.

The extension must call <i>DereferenceSwitchPort</i> if it had previously called <a href="https://msdn.microsoft.com/5FD2E931-AC9F-4157-9C45-F93261FC834D">ReferenceSwitchPort</a> for an extensible switch port. 




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598204">NdisFGetOptionalSwitchHandlers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598273">OID_SWITCH_PORT_DELETE</a>



<a href="https://msdn.microsoft.com/5FD2E931-AC9F-4157-9C45-F93261FC834D">ReferenceSwitchPort</a>
 

 

