---
UID: NF:ucmmanager.UcmConnectorTypeCCurrentAdChanged
title: UcmConnectorTypeCCurrentAdChanged function (ucmmanager.h)
description: Notifies the USB connector manager framework extension (UcmCx) when the specified connector changes the current advertisement. Either the connector changes it (when it is DFP/Source), or the partner changed it (when it is UFP/Sink).
old-location: buses\ucmconnectortypeccurrentadchanged.htm
tech.root: usbref
ms.assetid: 26C4D840-2287-4DC2-B039-FD8D2FB92288
ms.date: 05/07/2018
keywords: ["UcmConnectorTypeCCurrentAdChanged function"]
ms.keywords: UcmConnectorTypeCCurrentAdChanged, UcmConnectorTypeCCurrentAdChanged method [Buses], buses.ucmconnectortypeccurrentadchanged, ucmmanager/UcmConnectorTypeCCurrentAdChanged
f1_keywords:
 - "ucmmanager/UcmConnectorTypeCCurrentAdChanged"
 - "UcmConnectorTypeCCurrentAdChanged"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- UcmCxstub.lib
- UcmCxstub.dll
api_name:
- UcmConnectorTypeCCurrentAdChanged
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcmConnectorTypeCCurrentAdChanged function


## -description


Notifies the USB connector manager framework extension (UcmCx) when the specified connector changes the current advertisement. Either the connector changes it (when it is DFP/Source), or the partner changed it (when it is UFP/Sink).


## -parameters




### -param Connector [in]

Handle to the connector object that the client driver received in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>.


### -param CurrentAdvertisement [in]

The new current advertisement of the connector indicated by one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_typec_current">UCM_TYPEC_CURRENT</a>-typed flags.


## -returns



<b>UcmConnectorTypeCCurrentAdChanged</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> value. 




## -remarks



When using a Type-C connector for charging, the partner connector sends a current advertisement when it's attached to the local connector. That initial advertisement is report to UcmCx  by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectortypecattach">UcmConnectorTypeCAttach</a>.  During the lifetime of the connection, the current level advertised by the source might change. The client driver must notify UcmCx about  that change by calling method. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectortypecattach">UcmConnectorTypeCAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectortypeccurrentadchanged">UcmConnectorTypeCCurrentAdChanged</a>
 

 

