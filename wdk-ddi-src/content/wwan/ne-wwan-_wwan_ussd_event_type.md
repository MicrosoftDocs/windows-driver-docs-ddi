---
UID: NE:wwan._WWAN_USSD_EVENT_TYPE
title: "_WWAN_USSD_EVENT_TYPE"
author: windows-driver-content
description: The WWAN_USSD_EVENT_TYPE enumeration lists the different types of Unstructured Supplementary Service Data (USSD) events.
old-location: netvista\wwan_ussd_event_type.htm
tech.root: netvista
ms.assetid: CEBC8A75-03E9-4E2A-9092-2FA3005371FE
ms.date: 05/02/2018
ms.keywords: "*PWWAN_USSD_EVENT_TYPE, WWAN_USSD_EVENT_TYPE, WWAN_USSD_EVENT_TYPE enumeration [Network Drivers Starting with Windows Vista], WwanUssdEventActionRequired, WwanUssdEventNetworkTimeOut, WwanUssdEventNoActionRequired, WwanUssdEventOperationNotSupported, WwanUssdEventOtherLocalClient, WwanUssdEventTerminated, _WWAN_USSD_EVENT_TYPE, netvista.wwan_ussd_event_type, wwan/WWAN_USSD_EVENT_TYPE, wwan/WwanUssdEventActionRequired, wwan/WwanUssdEventNetworkTimeOut, wwan/WwanUssdEventNoActionRequired, wwan/WwanUssdEventOperationNotSupported, wwan/WwanUssdEventOtherLocalClient, wwan/WwanUssdEventTerminated"
ms.topic: enum
req.header: wwan.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
-	wwan.h
api_name:
-	WWAN_USSD_EVENT_TYPE
product:
- Windows
targetos: Windows
req.typenames: WWAN_USSD_EVENT_TYPE, *PWWAN_USSD_EVENT_TYPE
---

# _WWAN_USSD_EVENT_TYPE enumeration


## -description


The WWAN_USSD_EVENT_TYPE enumeration lists the different types of Unstructured Supplementary Service Data (USSD) events.


## -enum-fields




### -field WwanUssdEventNoActionRequired

Indicates no further action is required or information needed.


### -field WwanUssdEventActionRequired

Indicates the USSD session is still open and further information is needed, such as additional USSD strings.


### -field WwanUssdEventTerminated

Indicates the USSD session has been terminated.


### -field WwanUssdEventOtherLocalClient

Indicates an active USSD session already exists and that a new session cannot be established until the active session terminates. This includes sessions that are invisible to the MB stack such as a USSD session termination in the Subscriber Identity Module (SIM).


### -field WwanUssdEventOperationNotSupported

Indicates that the previous request is not supported by the miniport driver or MB device.


### -field WwanUssdEventNetworkTimeOut

Indicates that the USSD session was closed due to a session time-out either locally or by the network. The miniport driver or MB device is responsible for timing out an inactive USSD session after an implementation-specific time-out.


## -remarks



Network-initiated USSD events use <i>WwanUssdEventActionRequired</i> to indicate when further information is needed after an MB device initiated operation. <i>WwanUssdEventActionRequired</i> events also indicate that the session is still open. All other events indicate that the existing USSD session has been closed.

<i>WwanUssdEventNoActionRequired</i> and <i>WwanUssdEventActionRequired</i> are the only events that require a non-empty USSD string to accompany them with a string length from 1 to 160 bytes. All other events must set the USSD string length to 0 to indicate that the string is empty.

The value of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh464136">WWAN_USSD_EVENT</a><b>SessionState</b> member is ignored if no string is present.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh464136">WWAN_USSD_EVENT</a>
 

 

