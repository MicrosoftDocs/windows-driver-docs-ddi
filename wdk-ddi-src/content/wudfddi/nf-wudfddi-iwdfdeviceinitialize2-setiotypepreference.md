---
UID: NF:wudfddi.IWDFDeviceInitialize2.SetIoTypePreference
title: IWDFDeviceInitialize2::SetIoTypePreference (wudfddi.h)
description: The SetIoTypePreference method specifies your preferences for how UMDF and the driver access the data buffers of a device's I/O requests.
old-location: wdf\iwdfdeviceinitialize2_setiotypepreference.htm
tech.root: wdf
ms.assetid: 7d79f34d-42aa-4ac7-a63d-2f17ee0dfcf0
ms.date: 02/26/2018
ms.keywords: IWDFDeviceInitialize2 interface,SetIoTypePreference method, IWDFDeviceInitialize2.SetIoTypePreference, IWDFDeviceInitialize2::SetIoTypePreference, SetIoTypePreference, SetIoTypePreference method, SetIoTypePreference method,IWDFDeviceInitialize2 interface, UMDFDeviceObjectRef_33317875-3e52-47fc-9d6b-0e886f802dde.xml, umdf.iwdfdeviceinitialize2_setiotypepreference, wdf.iwdfdeviceinitialize2_setiotypepreference, wudfddi/IWDFDeviceInitialize2::SetIoTypePreference
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFDeviceInitialize2.SetIoTypePreference
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDeviceInitialize2::SetIoTypePreference


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetIoTypePreference</b> method specifies your preferences for how UMDF and the driver access the data buffers of a device's I/O requests.


## -parameters




### -param RetrievalMode [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561399">WDF_DEVICE_IO_BUFFER_RETRIEVAL</a>-typed value that specifies the buffer retrieval mode that you prefer UMDF to use to make an I/O request's buffers available to the driver.


### -param ReadWritePreference [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551255">WDF_DEVICE_IO_TYPE</a>-typed value that specifies the buffer access method that you prefer UMDF to use for the data buffers of read and write requests. 


### -param IoControlPreference [in]

A WDF_DEVICE_IO_TYPE-typed value that specifies the buffer access method that you prefer UMDF to use for the data buffers of device I/O control requests. 


## -returns



None.




## -remarks



If a driver calls <b>SetIoTypePreference</b> for a device, it must do so from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff554896">IDriverEntry::OnDeviceAdd</a> callback function, before the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.

If the driver does not call <b>SetIoTypePreference</b>, UMDF sets the <i>RetrievalMode</i> parameter to <b>WdfDeviceIoBufferRetrievalCopyImmediately</b> and it sets the buffer access method to <b>WdfDeviceIoBuffered</b> for read, write, and device I/O control requests.

UMDF might not use the preferences that the driver specifies when it calls <b>SetIoTypePreference</b>. For more information about how UMDF chooses a retrieval mode and buffer access method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Specifying a Buffer Retrieval Mode</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">How UMDF Chooses a Buffer Access Method for an I/O Request</a><u>.</u>

A driver cannot set the buffer access method to <b>WdfDeviceIoDirect</b> or <b>WdfDeviceIoBufferedOrDirect</b> unless it also sets the <i>RetrievalMode</i> parameter to <b>WdfDeviceIoBufferRetrievalDeferred</b>.

For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.


#### Examples

The following code example shows a segment of a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554896">IDriverEntry::OnDeviceAdd</a> callback function. The segment obtains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556967">IWDFDeviceInitialize2</a> interface and then calls <b>SetIoTypePreference</b>. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT
 CMyDriver::OnDeviceAdd(
    __in IWDFDriver *FxWdfDriver,
    __in IWDFDeviceInitialize *FxDeviceInit
    )
{
...
    //
    // Declare an IWDFDeviceInitialize2 interface pointer and obtain the
    // IWDFDeviceInitialize2 interface from the IWDFDeviceInitialize interface.
    //
    CComQIPtr<IWDFDeviceInitialize2> di2 = FxDeviceInit;

    //
    // For this device, set the retrieval mode to deferred, set
    // the access method to buffered for read and write requests,
    // and set the access mode to direct for device I/O control requests.
    // 
    di2->SetIoTypePreference(WdfDeviceIoBufferRetrievalDeferred,
                             WdfDeviceIoBuffered,
                             WdfDeviceIoDirect);
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556967">IWDFDeviceInitialize2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558994">IWDFIoRequest2::GetEffectiveIoType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561399">WDF_DEVICE_IO_BUFFER_RETRIEVAL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561404">WDF_DEVICE_IO_TYPE (UMDF)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546128">WdfDeviceInitSetIoType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265604">WdfDeviceInitSetIoTypeEx</a>
 

 

