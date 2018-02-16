---
UID: NF:ucmmanager.UcmConnectorTypeCCurrentAdChanged
title: UcmConnectorTypeCCurrentAdChanged function
author: windows-driver-content
description: Notifies the USB connector manager framework extension (UcmCx) when the specified connector changes the current advertisement. Either the connector changes it (when it is DFP/Source), or the partner changed it (when it is UFP/Sink).
old-location: buses\ucmconnectortypeccurrentadchanged.htm
old-project: usbref
ms.assetid: 26C4D840-2287-4DC2-B039-FD8D2FB92288
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: ucmmanager/UcmConnectorTypeCCurrentAdChanged, UcmConnectorTypeCCurrentAdChanged method [Buses], buses.ucmconnectortypeccurrentadchanged, UcmConnectorTypeCCurrentAdChanged
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	UcmCxstub.lib
-	UcmCxstub.dll
apiname:
-	UcmConnectorTypeCCurrentAdChanged
product: Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---

# UcmConnectorTypeCCurrentAdChanged function


## -description


Notifies the USB connector manager framework extension (UcmCx) when the specified connector changes the current advertisement. Either the connector changes it (when it is DFP/Source), or the partner changed it (when it is UFP/Sink).


## -syntax


````
NTSTATUS UcmConnectorTypeCCurrentAdChanged(
  [in] UCMCONNECTOR      Connector,
  [in] UCM_TYPEC_CURRENT CurrentAdvertisement
);
````


## -parameters




### -param Connector [in]

Handle to the connector object that the client driver received in the previous call to <a href="..\ucmmanager\nf-ucmmanager-ucmconnectorcreate.md">UcmConnectorCreate</a>.


### -param CurrentAdvertisement [in]

The new current advertisement of the connector indicated by one of the <a href="..\ucmtypes\ne-ucmtypes-_ucm_typec_current.md">UCM_TYPEC_CURRENT</a>-typed flags.


## -returns



<b>UcmConnectorTypeCCurrentAdChanged</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value. 




## -remarks



When using a Type-C connector for charging, the partner connector sends a current advertisement when it's attached to the local connector. That initial advertisement is report to UcmCx  by calling <a href="..\ucmmanager\nf-ucmmanager-ucmconnectortypecattach.md">UcmConnectorTypeCAttach</a>.  During the lifetime of the connection, the current level advertised by the source might change. The client driver must notify UcmCx about  that change by calling method. 




## -see-also

<a href="..\ucmmanager\nf-ucmmanager-ucmconnectortypeccurrentadchanged.md">UcmConnectorTypeCCurrentAdChanged</a>



<a href="..\ucmmanager\nf-ucmmanager-ucmconnectorcreate.md">UcmConnectorCreate</a>



<a href="..\ucmmanager\nf-ucmmanager-ucmconnectortypecattach.md">UcmConnectorTypeCAttach</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmConnectorTypeCCurrentAdChanged method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

