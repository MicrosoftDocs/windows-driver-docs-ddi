---
UID: NS:ucxroothub._UCX_ROOTHUB_CONFIG
title: "_UCX_ROOTHUB_CONFIG" (ucxroothub.h)
description: Contains pointers to event callback functions for creating the root hub by calling UcxRootHubCreate. Initialize this structure by calling UCX_ROOTHUB_CONFIG_INIT initialization function (see Ucxclass.h).
old-location: buses\_ucx_roothub_config.htm
tech.root: usbref
ms.assetid: 27E54F0D-2163-4D7C-B204-336EE0227488
ms.date: 05/07/2018
ms.keywords: "*PUCX_ROOTHUB_CONFIG, P_UCX_ROOTHUB_CONFIG, P_UCX_ROOTHUB_CONFIG structure pointer [Buses], UCX_ROOTHUB_CONFIG, UCX_ROOTHUB_CONFIG structure [Buses], _UCX_ROOTHUB_CONFIG, buses._ucx_roothub_config, ucxroothub/P_UCX_ROOTHUB_CONFIG, ucxroothub/_UCX_ROOTHUB_CONFIG"
ms.topic: struct
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxroothub.h
api_name:
-	UCX_ROOTHUB_CONFIG
product:
- Windows
targetos: Windows
req.typenames: UCX_ROOTHUB_CONFIG, *PUCX_ROOTHUB_CONFIG
---

# _UCX_ROOTHUB_CONFIG structure


## -description


Contains pointers to event callback functions for creating the root hub by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt188048">UcxRootHubCreate</a>. Initialize this structure by calling <b>UCX_ROOTHUB_CONFIG_INIT</b> initialization function (see Ucxclass.h).


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field NumberOfPresentedControlUrbCallbacks

The number of control requests sent to the default endpoint.


### -field EvtRootHubClearHubFeature

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187833">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.


### -field EvtRootHubClearPortFeature

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187833">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.


### -field EvtRootHubGetHubStatus

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187833">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.


### -field EvtRootHubGetPortStatus

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187833">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.


### -field EvtRootHubSetHubFeature

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187833">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.


### -field EvtRootHubSetPortFeature

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187833">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.


### -field EvtRootHubGetPortErrorCount

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187833">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.


### -field EvtRootHubControlUrb

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187833">EVT_UCX_ROOTHUB_CONTROL_URB</a> callback function.


### -field EvtRootHubInterruptTx

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187837">EVT_UCX_ROOTHUB_INTERRUPT_TX</a> callback function.


### -field EvtRootHubGetInfo

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187836">EVT_UCX_ROOTHUB_GET_INFO</a> callback function.


### -field EvtRootHubGet20PortInfo

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187834">EVT_UCX_ROOTHUB_GET_20PORT_INFO</a> callback function.


### -field EvtRootHubGet30PortInfo

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187835">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a> callback function.


### -field WdfRequestAttributes

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies initialization parameters.

