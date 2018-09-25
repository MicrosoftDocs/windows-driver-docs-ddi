---
UID: NF:ucmmanager.UcmConnectorPdConnectionStateChanged
title: UcmConnectorPdConnectionStateChanged function
author: windows-driver-content
description: Notifies the USB connector manager framework extension (UcmCx) with the connection capabilities of the currently negotiated PD contract (if any).
old-location: buses\ucmconnectorpdconnectionstatechanged.htm
tech.root: usbref
ms.assetid: 2DE78869-9AFC-423A-BCB0-B7BBAB0C06BC
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: UcmConnectorPdConnectionStateChanged, UcmConnectorPdConnectionStateChanged method [Buses], buses.ucmconnectorpdconnectionstatechanged, ucmmanager/UcmConnectorPdConnectionStateChanged
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmmanager.h
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
req.lib: UcmCxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	UcmCxstub.lib
-	UcmCxstub.dll
api_name:
-	UcmConnectorPdConnectionStateChanged
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcmConnectorPdConnectionStateChanged function


## -description


Notifies the USB connector manager framework extension (UcmCx) with the connection capabilities of the currently negotiated PD contract (if any).


## -parameters




### -param Connector [in]

Handle to the connector object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>.


### -param Params [in]

Pointer to a  <a href="https://msdn.microsoft.com/library/windows/hardware/mt187926">UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS</a> structure contains driver-supplied state of the connector.


## -returns



<b>UcmConnectorPdConnectionStateChanged</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>
 

 

