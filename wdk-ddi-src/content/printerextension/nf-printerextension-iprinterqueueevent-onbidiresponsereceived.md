---
UID: NF:printerextension.IPrinterQueueEvent.OnBidiResponseReceived
title: IPrinterQueueEvent::OnBidiResponseReceived method
author: windows-driver-content
description: Called when a bidi response is received.
old-location: print\iprinterqueueevent_onbidiresponsereceived.htm
old-project: print
ms.assetid: D0CD9950-DF73-4D46-B901-FA45BA88D3CF
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.iprinterqueueevent_onbidiresponsereceived, IPrinterQueueEvent::OnBidiResponseReceived, OnBidiResponseReceived method [Print Devices], IPrinterQueueEvent interface, IPrinterQueueEvent interface [Print Devices], OnBidiResponseReceived method, OnBidiResponseReceived method [Print Devices], printerextension/IPrinterQueueEvent::OnBidiResponseReceived, IPrinterQueueEvent, OnBidiResponseReceived
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrinterQueueEvent.OnBidiResponseReceived
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterQueueEvent::OnBidiResponseReceived method


## -description


Called when a bidi response  is received.


## -syntax


````
HRESULT OnBidiResponseReceived(
  [in] BSTR    bstrResponse,
  [in] HRESULT hrStatus
);
````


## -parameters




### -param bstrResponse [in]

The received response.


### -param hrStatus [in]

An HRESULT value.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



The <i>bstrResponse</i> parameter is formatted according to the schema that is described in <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/dd183368(v=vs.85).aspx">Bidi Request and Response Schemas</a>.




## -see-also

<a href="https://msdn.microsoft.com/E98A121A-514A-4437-A542-E8629697B7EA">IPrinterQueue::SendBidiQuery</a>



<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/dd183368(v=vs.85).aspx">Bidi Request and Response Schemas</a>



<a href="..\printerextension\nn-printerextension-iprinterqueue.md">IPrinterQueue</a>



<a href="..\printerextension\nn-printerextension-iprinterqueueevent.md">IPrinterQueueEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueueEvent::OnBidiResponseReceived method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

