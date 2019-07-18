---
UID: NF:wdfrequest.WdfRequestGetEffectiveIoType
title: WdfRequestGetEffectiveIoType function (wdfrequest.h)
description: The WdfRequestGetEffectiveIoType method returns the buffer access method that UMDF is using for the data buffers of the specified I/O request.
old-location: wdf\wdfrequestgeteffectiveiotype.htm
tech.root: wdf
ms.assetid: ED63E47F-B91F-49DC-9CE9-8CFE8F670B16
ms.date: 02/26/2018
ms.keywords: WdfRequestGetEffectiveIoType, WdfRequestGetEffectiveIoType method, wdf.wdfrequestgeteffectiveiotype, wdfrequest/WdfRequestGetEffectiveIoType
ms.topic: function
f1_keywords:
 - "wdfrequest/WdfRequestGetEffectiveIoType"
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
req.dll: WUDFx02000.dll
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- WUDFx02000.dll
api_name:
- WdfRequestGetEffectiveIoType
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestGetEffectiveIoType function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WdfRequestGetEffectiveIoType</b> method returns the buffer access method that UMDF is using for the data buffers of the specified I/O request.


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestGetEffectiveIoType</b> returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ne-wdfdevice-_wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>-typed value that identifies the buffer access method that UMDF is using for the I/O request's data buffers. 




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-buffer-access-methods-in-umdf-drivers">Managing Buffer Access Methods in UMDF Drivers</a>.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_write">EvtIoWrite</a> callback function can determine the buffer access method for the specified write request.

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ne-wdfdevice-_wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>
 

 

