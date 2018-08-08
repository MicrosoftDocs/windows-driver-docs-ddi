---
UID: NF:ucmmanager.UcmConnectorChargingStateChanged
title: UcmConnectorChargingStateChanged function
author: windows-driver-content
description: Notifies the USB connector manager framework extension (UcmCx) with the updated charging state of the partner connector.
old-location: buses\ucmconnectorchargingstatechanged.htm
tech.root: usbref
ms.assetid: A645BFE0-4B7F-416F-9096-596ADAA37951
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: UcmConnectorChargingStateChanged, UcmConnectorChargingStateChanged method [Buses], buses.ucmconnectorchargingstatechanged, ucmmanager/UcmConnectorChargingStateChanged
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
-	UcmConnectorChargingStateChanged
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcmConnectorChargingStateChanged function


## -description


Notifies the USB connector manager framework extension (UcmCx) with the updated charging state of the partner connector.


## -parameters




### -param Connector [in]

Handle to the connector object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>.


### -param ChargingState [in]

One of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187921">UCM_CHARGING_STATE</a>-typed flags that indicates the new charging state. 


## -returns



<b>UcmConnectorChargingStateChanged</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value. 




## -remarks



If the client driver determines that the charging state is non-optimal, it should report slow or trickle charging to UcmCx. Then, the operating system notifies the user of this condition.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>
 

 

