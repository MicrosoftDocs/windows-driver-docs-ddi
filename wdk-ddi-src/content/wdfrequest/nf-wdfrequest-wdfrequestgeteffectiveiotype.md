---
UID: NF:wdfrequest.WdfRequestGetEffectiveIoType
title: WdfRequestGetEffectiveIoType function
author: windows-driver-content
description: The WdfRequestGetEffectiveIoType method returns the buffer access method that UMDF is using for the data buffers of the specified I/O request.
old-location: wdf\wdfrequestgeteffectiveiotype.htm
old-project: wdf
ms.assetid: ED63E47F-B91F-49DC-9CE9-8CFE8F670B16
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfrequest/WdfRequestGetEffectiveIoType, PFN_WDFREQUESTGETEFFECTIVEIOTYPE, wdf.wdfrequestgeteffectiveiotype, WdfRequestGetEffectiveIoType method, WdfRequestGetEffectiveIoType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll; TBD
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	WUDFx02000.dll
apiname:
-	WdfRequestGetEffectiveIoType
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestGetEffectiveIoType function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfRequestGetEffectiveIoType</b> method returns the buffer access method that UMDF is using for the data buffers of the specified I/O request.


## -syntax


````
WDF_DEVICE_IO_TYPE WdfRequestGetEffectiveIoType(
  _In_ WDFREQUEST Request
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestGetEffectiveIoType</b> returns a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>-typed value that identifies the buffer access method that UMDF is using for the I/O request's data buffers. 




## -remarks



For more information, see <a href="https://msdn.microsoft.com/BDB78BCD-1964-431B-BE99-CABA6DF44D7A">Managing Buffer Access Methods in UMDF Drivers</a>.


#### Examples

The following code example shows how an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_write.md">EvtIoWrite</a> callback function can determine the buffer access method for the specified write request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyDrvEvtIoWrite(
  _In_  WDFQUEUE Queue,
  _In_  WDFREQUEST Request,
  _In_  size_t Length
)
{ 

...

    WDF_DEVICE_IO_TYPE iotype = WdfDeviceIoUndefined;
    
    iotype = WdfRequestGetEffectiveIoType(Request);

...

}
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestGetEffectiveIoType method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

