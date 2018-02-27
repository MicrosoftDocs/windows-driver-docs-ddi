---
UID: NE:fwpsk.FWPS_CONNECTION_REDIRECT_STATE_
title: FWPS_CONNECTION_REDIRECT_STATE_
author: windows-driver-content
description: The FWPS_CONNECTION_REDIRECT_STATE enumeration type specifies the current redirection state of a connection.
old-location: netvista\fwps_connection_redirect_state.htm
old-project: netvista
ms.assetid: f4fe8136-8a7c-499a-9f2c-1367138e5f30
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FWPS_CONNECTION_NOT_REDIRECTED, FWPS_CONNECTION_PREVIOUSLY_REDIRECTED_BY_SELF, FWPS_CONNECTION_REDIRECTED_BY_OTHER, FWPS_CONNECTION_REDIRECTED_BY_SELF, FWPS_CONNECTION_REDIRECT_STATE, FWPS_CONNECTION_REDIRECT_STATE enumeration [Network Drivers Starting with Windows Vista], FWPS_CONNECTION_REDIRECT_STATE_, FWPS_CONNECTION_REDIRECT_STATE_MAX, fwpsk/FWPS_CONNECTION_NOT_REDIRECTED, fwpsk/FWPS_CONNECTION_PREVIOUSLY_REDIRECTED_BY_SELF, fwpsk/FWPS_CONNECTION_REDIRECTED_BY_OTHER, fwpsk/FWPS_CONNECTION_REDIRECTED_BY_SELF, fwpsk/FWPS_CONNECTION_REDIRECT_STATE, fwpsk/FWPS_CONNECTION_REDIRECT_STATE_MAX, netvista.fwps_connection_redirect_state
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fwpsk.h
apiname:
-	FWPS_CONNECTION_REDIRECT_STATE
product: Windows
targetos: Windows
req.typenames: FWPS_CONNECTION_REDIRECT_STATE
---

# FWPS_CONNECTION_REDIRECT_STATE_ enumeration


## -description


The FWPS_CONNECTION_REDIRECT_STATE enumeration type specifies the current redirection state of a connection.


## -syntax


````
typedef enum FWPS_CONNECTION_REDIRECT_STATE_ { 
  FWPS_CONNECTION_NOT_REDIRECTED,
  FWPS_CONNECTION_REDIRECTED_BY_SELF,
  FWPS_CONNECTION_REDIRECTED_BY_OTHER,
  FWPS_CONNECTION_PREVIOUSLY_REDIRECTED_BY_SELF,
  FWPS_CONNECTION_REDIRECT_STATE_MAX
} FWPS_CONNECTION_REDIRECT_STATE;
````


## -enum-fields




### -field FWPS_CONNECTION_NOT_REDIRECTED

The connection was not redirected.


### -field FWPS_CONNECTION_REDIRECTED_BY_SELF

The connection was redirected by the calling redirect handle.


### -field FWPS_CONNECTION_REDIRECTED_BY_OTHER

The connection was redirected by a different redirect handle.


### -field FWPS_CONNECTION_PREVIOUSLY_REDIRECTED_BY_SELF

The connection was redirected by the calling redirect handle but later redirected again by a different redirect handle.


### -field FWPS_CONNECTION_REDIRECT_STATE_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.


## -remarks



The FWPS_CONNECTION_REDIRECT_STATE enumeration is the return type for a call to the <a href="..\fwpsk\nf-fwpsk-fwpsqueryconnectionredirectstate0.md">FwpsQueryConnectionRedirectState0</a>  function.




## -see-also

<a href="..\fwpsk\nf-fwpsk-fwpsqueryconnectionredirectstate0.md">FwpsQueryConnectionRedirectState0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_CONNECTION_REDIRECT_STATE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

