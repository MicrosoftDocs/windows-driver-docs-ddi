---
UID: NF:ucmmanager.UcmConnectorTypeCDetach
title: UcmConnectorTypeCDetach function
author: windows-driver-content
description: Notifies the USB connector manager framework extension (UcmCx) when the partner connector detaches from the specified Type-C connector.
old-location: buses\ucmconnectortypecdetach.htm
old-project: usbref
ms.assetid: E89DC8B6-9379-4FE2-BF4C-897DA9DFA11C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ucmconnectortypecdetach, ucmmanager/UcmConnectorTypeCDetach, UcmConnectorTypeCDetach method [Buses], UcmConnectorTypeCDetach
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
-	UcmConnectorTypeCDetach
product: Windows
targetos: Windows
req.typenames: *PPORT_DATA_1, PORT_DATA_1
req.product: Windows 10 or later.
---

# UcmConnectorTypeCDetach function


## -description


Notifies the USB connector manager framework extension (UcmCx) when the partner connector  detaches from the specified Type-C connector.


## -syntax


````
NTSTATUS UcmConnectorTypeCDetach(
  [in] UCMCONNECTOR  Connector
);
````


## -parameters




### -param Connector [in]

Handle to the connector object that the client driver received in the previous call to <a href="..\ucmmanager\nf-ucmmanager-ucmconnectorcreate.md">UcmConnectorCreate</a>.


## -returns


<b>UcmConnectorTypeCDetach</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value. 



## -see-also

<a href="..\ucmmanager\nf-ucmmanager-ucmconnectortypecattach.md">UcmConnectorTypeCAttach</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmConnectorTypeCDetach method%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

