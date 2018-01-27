---
UID: NE:ucmtypes._UCM_PD_CONN_STATE
title: _UCM_PD_CONN_STATE
author: windows-driver-content
description: Defines power delivery (PD) negotiation states of a Type-C port.
old-location: buses\ucm_pd_conn_state.htm
old-project: usbref
ms.assetid: 7D146DDF-58A5-40C2-BF21-AF785DC7DB18
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UcmPdConnStateNegotiationFailed, UCM_PD_CONN_STATE, UcmPdConnStateNotSupported, ucmtypes/UCM_PD_CONN_STATE, _UCM_PD_CONN_STATE, ucmtypes/UcmPdConnStateNotSupported, UcmPdConnStateNegotiationSucceeded, ucmtypes/UcmPdConnStateInvalid, UCM_PD_CONN_STATE enumeration [Buses], buses.ucm_pd_conn_state, UcmPdConnStateInvalid, ucmtypes/UcmPdConnStateNegotiationSucceeded, ucmtypes/UcmPdConnStateNegotiationFailed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ucmtypes.h
apiname: 
-	UCM_PD_CONN_STATE
product: Windows
targetos: Windows
req.typenames: UCM_PD_CONN_STATE
req.product: Windows 10 or later.
---

# _UCM_PD_CONN_STATE enumeration


## -description


Defines power delivery (PD) negotiation states of a Type-C port.


## -syntax


````
typedef enum _UCM_PD_CONN_STATE { 
  UcmPdConnStateInvalid               = 0x0,
  UcmPdConnStateNotSupported,
  UcmPdConnStateNegotiationFailed,
  UcmPdConnStateNegotiationSucceeded
} UCM_PD_CONN_STATE;
````


## -enum-fields




### -field UcmPdConnStateInvalid

Indicates the PD negotiation state is invalid.


### -field UcmPdConnStateNotSupported

Indicates a PD connection is not supported. 


### -field UcmPdConnStateNegotiationFailed

Indicates the PD negotiation failed.


### -field UcmPdConnStateNegotiationSucceeded

Indicates the PD negotiation succeeded.


## -see-also

<a href="..\ucmmanager\nf-ucmmanager-ucmconnectorpdconnectionstatechanged.md">UcmConnectorPdConnectionStateChanged</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_PD_CONN_STATE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

