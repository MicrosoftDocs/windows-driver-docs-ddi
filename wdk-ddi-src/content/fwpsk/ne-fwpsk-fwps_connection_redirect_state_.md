---
UID: NE:fwpsk.FWPS_CONNECTION_REDIRECT_STATE_
title: FWPS_CONNECTION_REDIRECT_STATE_
author: windows-driver-content
description: The FWPS_CONNECTION_REDIRECT_STATE enumeration type specifies the current redirection state of a connection.
old-location: netvista\fwps_connection_redirect_state.htm
old-project: netvista
ms.assetid: f4fe8136-8a7c-499a-9f2c-1367138e5f30
ms.author: windowsdriverdev
ms.date: 4/25/2018
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_CONNECTION_REDIRECT_STATE
product: Windows
targetos: Windows
req.typenames: FWPS_CONNECTION_REDIRECT_STATE
---

# FWPS_CONNECTION_REDIRECT_STATE_ enumeration


## -description


The FWPS_CONNECTION_REDIRECT_STATE enumeration type specifies the current redirection state of a connection.


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



The FWPS_CONNECTION_REDIRECT_STATE enumeration is the return type for a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439677">FwpsQueryConnectionRedirectState0</a>  function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439677">FwpsQueryConnectionRedirectState0</a>
 

 

