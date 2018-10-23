---
UID: NF:ucmmanager.UcmConnectorPdSourceCaps
title: UcmConnectorPdSourceCaps function
author: windows-driver-content
description: Notifies the USB connector manager framework extension (UcmCx) with the power source capabilities of the connector.
old-location: buses\ucmconnectorpdsourcecaps.htm
tech.root: usbref
ms.assetid: 7C52EE60-7903-42A7-B535-9B8ED7A4B021
ms.date: 05/07/2018
ms.keywords: UcmConnectorPdSourceCaps, UcmConnectorPdSourceCaps method [Buses], buses.ucmconnectorpdsourcecaps, ucmmanager/UcmConnectorPdSourceCaps
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
-	UcmConnectorPdSourceCaps
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcmConnectorPdSourceCaps function


## -description


Notifies the USB connector manager framework extension (UcmCx) with the power source capabilities of the connector.


## -parameters




### -param Connector [in]

Handle to the connector object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>.


### -param Pdos

<p>A caller-allocated array of <a href="https://msdn.microsoft.com/library/Mt187935(v=VS.85).aspx"><b>UCM_PD_POWER_DATA_OBJECT</b></a> structures that describes the power source capabilities.</p>


### -param PdoCount [in]

Number of elements in the array specified by   <i>Pdos[]</i>.


## -returns



<b>UcmConnectorPdSourceCaps</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value. 




## -remarks



If the connector (local connector) is the power source, the client driver can report the  capabilities and changes to those capabilities to UcmCx by using <b>UcmConnectorPdSourceCaps</b>. If connector is a the power sink, report the advertised capabilities received from partner by calling  <a href="https://msdn.microsoft.com/library/windows/hardware/mt187912">UcmConnectorPdPartnerSourceCaps</a>. The client driver must call <b>UcmConnectorPdPartnerSourceCaps</b> each time the partner re-advertises its capabilities.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>
 

 

