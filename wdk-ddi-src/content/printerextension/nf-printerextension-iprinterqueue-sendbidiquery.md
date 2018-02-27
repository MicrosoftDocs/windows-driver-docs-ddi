---
UID: NF:printerextension.IPrinterQueue.SendBidiQuery
title: IPrinterQueue::SendBidiQuery method
author: windows-driver-content
description: Performs an asynchronous refresh operation with the specified query, and invokes the IPrinterQueueEvent::OnBidiResponseReceived method.
old-location: print\iprinterqueue_sendbidiquery.htm
old-project: print
ms.assetid: E98A121A-514A-4437-A542-E8629697B7EA
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrinterQueue, IPrinterQueue interface [Print Devices], SendBidiQuery method, IPrinterQueue::SendBidiQuery, SendBidiQuery method [Print Devices], SendBidiQuery method [Print Devices], IPrinterQueue interface, SendBidiQuery,IPrinterQueue.SendBidiQuery, print.iprinterqueue_sendbidiquery, printerextension/IPrinterQueue::SendBidiQuery
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
-	IPrinterQueue.SendBidiQuery
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterQueue::SendBidiQuery method


## -description


Performs an asynchronous refresh operation with the specified query, and invokes the <a href="https://msdn.microsoft.com/D0CD9950-DF73-4D46-B901-FA45BA88D3CF">IPrinterQueueEvent::OnBidiResponseReceived</a> method.


## -syntax


````
HRESULT SendBidiQuery(
  [in] BSTR bstrBidiQuery
);
````


## -parameters




### -param bstrBidiQuery [in]

The specified query.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



When the <b>SendBidiQuery</b> method is called, it immediately raises the <a href="https://msdn.microsoft.com/D0CD9950-DF73-4D46-B901-FA45BA88D3CF">IPrinterQueueEvent::OnBidiResponseReceived</a> event, if there is a cached response available.  The print system then starts an asynchronous operation to use the <a href="http://msdn.microsoft.com/en-us/library/dd183365(v=vs.85)">Bidi Communication Interfaces</a>. At this point <b>SendBidiQuery</b> returns, thus unblocking the caller.  When the asynchronous operation completes, the print system raises the <b>IPrinterQueueEvent::OnBidiResponseReceived</b> event again. <b>SendBidiQuery</b> is decoupled from its associated response on purpose. The decoupling is done because, in the case where there is no cached data, the resulting latency can be due to many factors and an immediate response cannot be expected.  Additionally the caller may receive multiple responses based on whether there is cached data, and whether there is a response from the device.

Using the <a href="http://msdn.microsoft.com/en-us/library/dd183365(v=vs.85)">Bidi Communication Interfaces</a> causes the port monitor to refresh the underlying requested values. In the case of USB, if a JavaScript component is available, then the JavaScript code is invoked to refresh the requested values.

The cache is also updated in the following situations:

<b>At predetermined intervals</b>


<dl>
<dd>For WSD devices the data is updated when the device reports changes via events.</dd>
<dd>For TCP &amp; USB devices the refresh interval is based on where the Bidi value is defined.
All standard Bidi values (as defined by the port monitor’s embedded Bidi files) are refreshed at an interval that is preset by the port monitors. If the specific Bidi Query is part of the IHV Bidi Extension, then the refresh interval is specified in the XML extension file for each individual value.</dd>
</dl>


<b>When printer configuration changes</b>


<dl>
<dd>For example, when a WSD-based device raises an event to let the spooler (WSDMon) know that something about the device has changed. In other words, the printer configuration has changed.</dd>
</dl>





## -see-also

<a href="http://msdn.microsoft.com/en-us/library/dd183365(v=vs.85)">Bidi Communication Interfaces</a>



<a href="..\printerextension\nn-printerextension-iprinterqueue.md">IPrinterQueue</a>



<a href="https://msdn.microsoft.com/D0CD9950-DF73-4D46-B901-FA45BA88D3CF">IPrinterQueueEvent::OnBidiResponseReceived</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueue::SendBidiQuery method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

