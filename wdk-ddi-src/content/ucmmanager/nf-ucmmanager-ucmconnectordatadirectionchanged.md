---
UID: NF:ucmmanager.UcmConnectorDataDirectionChanged
title: UcmConnectorDataDirectionChanged function
author: windows-driver-content
description: Notifies the USB connector manager framework extension (UcmCx) with the new data role of a change in data role.
old-location: buses\ucmconnectordatadirectionchanged.htm
tech.root: usbref
ms.assetid: 62ED07DF-2DDC-42FD-80C3-75AB3DE839AD
ms.date: 5/7/2018
ms.keywords: UcmConnectorDataDirectionChanged, UcmConnectorDataDirectionChanged method [Buses], buses.ucmconnectordatadirectionchanged, ucmmanager/UcmConnectorDataDirectionChanged
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
-	UcmConnectorDataDirectionChanged
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcmConnectorDataDirectionChanged function


## -description


Notifies the USB connector manager framework extension (UcmCx) with the new data role  of a change in data role.


## -parameters




### -param Connector [in]

Handle to the connector object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>.


### -param Success [in]

Used to indicate failure of a data-role swap that was initiated by UcmCx using <a href="https://msdn.microsoft.com/library/windows/hardware/mt187818">EVT_UCM_CONNECTOR_SET_DATA_ROLE</a>. 

If TRUE, the operation was successful. FALSE, otherwise.


### -param CurrentDataRole [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt187947">UCM_TYPEC_PARTNER</a> value that indicates the new data role. 


## -returns



<b>UcmConnectorDataDirectionChanged</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value. 




## -remarks



If the connector partner is attached, UcmCx updates the data role of the partner depending on the <i>CurrentDataRole</i> value. For example, if the client driver changes the data role to <b>UcmTypeCPortStateUfp</b>, UcmCx updates the role of the connector partner to <b>UcmTypeCPortStateDfp</b>.

UcmCx can change the data role of a connector, and invokes <a href="https://msdn.microsoft.com/library/windows/hardware/mt187818">EVT_UCM_CONNECTOR_SET_DATA_ROLE</a>. In response to that call, the client should perform the DR_Swap operation, and indicate success/failure of the operation by calling  <b>UcmConnectorDataDirectionChanged</b>.

Alternatively, the client driver might choose to perform a role-swap autonomously, or the partner might perform a role-swap. In either case, when the role-swap has completed, the driver must report the new role to UcmCx using <b>UcmConnectorDataDirectionChanged</b>.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>
 

 

