---
UID: NN:printerextension.IPrinterBidiSetRequestCallback
title: IPrinterBidiSetRequestCallback
author: windows-driver-content
description: Describes the signature of the callback object that receives the Bidi response.
old-location: print\iprinterbidisetrequestcallback.htm
old-project: print
ms.assetid: C85690D0-3CA7-46C7-B597-E36555879F08
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrinterBidiSetRequestCallback, IPrinterBidiSetRequestCallback interface [Print Devices], IPrinterBidiSetRequestCallback interface [Print Devices], described, print.iprinterbidisetrequestcallback, printerextension/IPrinterBidiSetRequestCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	IPrinterBidiSetRequestCallback
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterBidiSetRequestCallback interface


## -description


Describes the signature of the callback object that receives the Bidi response.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterBidiSetRequestCallback</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrinterBidiSetRequestCallback</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterBidiSetRequestCallback</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265386">Completed</a>
</td>
<td align="left" width="63%">
Invoked when the Bidi “Set”” operation is completed.

</td>
</tr>
</table> 


## -remarks



<b>IPrinterBidiSetRequestCallback</b> provides the Bidi response string, and <b>HRESULT</b> value returned from the <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/dd144984(v=vs.85).aspx">IBidiSpl2::SendRecvXmlString</a> method. In other words,  this interface provides the results of the attempt to send data to the device. 

<b>IPrinterBidiSetRequestCallback</b>  helps to make it possible to perform device maintenance from a UWP  device app or from a printer extension. For more information, see <a href="https://msdn.microsoft.com/310E92A9-F751-4346-9B2D-0578A136AD20">Device Maintenance</a>.




## -see-also

<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/dd144984(v=vs.85).aspx">IBidiSpl2::SendRecvXmlString</a>



<a href="https://msdn.microsoft.com/310E92A9-F751-4346-9B2D-0578A136AD20">Device Maintenance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265391">SendBidiSetRequestAsync</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterBidiSetRequestCallback interface%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

