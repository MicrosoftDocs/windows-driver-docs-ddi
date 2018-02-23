---
UID: NF:printerextension.IPrinterQueue2.GetPrinterQueueView
title: IPrinterQueue2::GetPrinterQueueView method
author: windows-driver-content
description: Retrieves an IPrinterQueueView object, and initializes the object with the range of jobs to be monitored.
old-location: print\iprinterqueue2_getprinterqueueview.htm
old-project: print
ms.assetid: C565288C-B014-4A92-9F50-1641EAA30D22
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: print.iprinterqueue2_getprinterqueueview, IPrinterQueue2, printerextension/IPrinterQueue2::GetPrinterQueueView, GetPrinterQueueView method [Print Devices], IPrinterQueue2 interface, GetPrinterQueueView, IPrinterQueue2 interface [Print Devices], GetPrinterQueueView method, IPrinterQueue2::GetPrinterQueueView, GetPrinterQueueView method [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
-	IPrinterQueue2.GetPrinterQueueView
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterQueue2::GetPrinterQueueView method


## -description


Retrieves an <a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a> object, and initializes the object with the range of jobs to be monitored.

This method allows the user to perform job management tasks from within a UWP  device app for printers.


## -syntax


````
HRESULT GetPrinterQueueView(
  [in]          ULONG              ulViewOffset,
  [in]          ULONG              ulViewSize,
  [out, retval] IPrinterQueueView ** ppJobView 
);
````


## -parameters




### -param ulViewOffset [in]

Indicates the start of the range of jobs to be monitored.


### -param ulViewSize [in]

Indicates the size or the range of jobs to be monitored.


### -param ppJobView [out, retval]

IPrinterQueueView object that shows the range of jobs to be monitored.


## -returns



If the method call is successful, <b>GetPrinterQueueView</b> returns S_OK.

Otherwise, if a call to <b>GetPrinterQueueView</b> results in an error condition, then one of the following <b>HRESULT</b> values can be returned.
	  <table>
<tr>
<th>HRESULT value</th>
<th>Description</th>
</tr>
<tr>
<td>E_ILLEGAL_METHOD_CALL</td>
<td>Indicates an attempt to retrieve more than one printer queue view object.</td>
</tr>
<tr>
<td>E_INVALIDARG</td>
<td>Indicates an attempt to create a view size larger than the maximum size.</td>
</tr>
</table>
 






## -remarks



Only one <a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a> object can be retrieved per <a href="..\printerextension\nn-printerextension-iprinterqueue2.md">IPrinterQueue2</a> object.
However it is possible to move around the single view that you retrieve. In other words, it is possible to  change the positions of the monitored jobs by invoking <a href="https://msdn.microsoft.com/DB3C0439-EB82-4E49-8FEA-003C1B4A9EE0">IPrinterQueueView::SetViewRange</a>.

<div class="alert"><b>Note</b>  There is work underway to implement a cap on the maximum size of the printer queue view.</div>
<div> </div>



## -see-also

<a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a>



<a href="..\printerextension\nn-printerextension-iprinterqueue2.md">IPrinterQueue2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueue2::GetPrinterQueueView method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

