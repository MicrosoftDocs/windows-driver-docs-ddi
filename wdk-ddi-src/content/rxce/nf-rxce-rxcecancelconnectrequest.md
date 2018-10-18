---
UID: NF:rxce.RxCeCancelConnectRequest
title: RxCeCancelConnectRequest function
author: windows-driver-content
description: RxCeCancelConnectRequest cancels a previously issued connection request. Note that this routine is not currently implemented.
old-location: ifsk\rxcecancelconnectrequest.htm
tech.root: ifsk
ms.assetid: 32893a68-68ac-4bac-ab0f-1d07a1e873f3
ms.date: 4/16/2018
ms.keywords: RxCeCancelConnectRequest, RxCeCancelConnectRequest routine [Installable File System Drivers], ifsk.rxcecancelconnectrequest, rxce/RxCeCancelConnectRequest, rxref_b7978600-a1ca-4713-b170-bc1f365f2f96.xml
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h
req.target-type: Desktop
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxce.h
api_name:
-	RxCeCancelConnectRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxCeCancelConnectRequest function


## -description


<b>RxCeCancelConnectRequest</b> cancels a previously issued connection request. Note that this routine is not currently implemented.


## -parameters




### -param pLocalAddress [in]

A pointer to the local RDBSS connection engine address on which the previously issued connection request was made.


### -param pServerName [in]

A pointer to the name of the server on which the previous connection request was made.


### -param pConnectionInformation [in]

A pointer to the connection information that specifies the remote address. on which the previously issued connection request was made.


## -returns



<b>RxCeCancelConnectRequest</b> returns STATUS_NOT_IMPLEMENTED since this routine is not currently implemented.




## -remarks



<b>RXCE_CONNECTION_INFORMATION</b> is a typedef for a <b>TDI_CONNECTION_INFORMATION</b> structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554321">RxCeTearDownConnection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565085">TDI_CONNECTION_INFORMATION</a>
 

 

