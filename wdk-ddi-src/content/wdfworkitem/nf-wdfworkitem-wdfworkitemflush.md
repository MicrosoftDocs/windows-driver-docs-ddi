---
UID: NF:wdfworkitem.WdfWorkItemFlush
title: WdfWorkItemFlush function
author: windows-driver-content
description: The WdfWorkItemFlush method returns after a specified work item has been serviced.
old-location: wdf\wdfworkitemflush.htm
old-project: wdf
ms.assetid: 5868dd01-17ba-4edf-b665-c90d2b1aa2ba
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWorkItemObjectRef_620a50e7-1995-4806-b71a-932f7fc7c35a.xml, WdfWorkItemFlush, WdfWorkItemFlush method, kmdf.wdfworkitemflush, wdf.wdfworkitemflush, wdfworkitem/WdfWorkItemFlush
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfworkitem.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfWorkItemFlush
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_CONFIG, *PWDF_WMI_PROVIDER_CONFIG
req.product: Windows 10 or later.
---

# WdfWorkItemFlush function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfWorkItemFlush</b> method returns after a specified work item has been serviced.


## -parameters




### -param WorkItem [in]

A handle to a framework work-item object that is obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551201">WdfWorkItemCreate</a>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If your driver calls the <b>WdfWorkItemFlush</b> method, the method does not return until a system worker thread has removed the specified work item from the work-item queue and called the driver's <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function, and the <i>EvtWorkItem</i> callback function has subsequently returned after processing the work item.

Most drivers that use work items do not need to call <b>WdfWorkItemFlush</b>. A driver might call <b>WdfWorkItemFlush</b> if it must synchronize completion of work items with the removal of a remote I/O target. In this case, the driver can call <b>WdfWorkItemFlush</b> from within its <a href="https://msdn.microsoft.com/cb7c97e5-081e-44fc-a759-9a1ae81de41c">EvtIoTargetQueryRemove</a> callback function. 

For more information about work items, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.


#### Examples

The following code example is an <a href="https://msdn.microsoft.com/cb7c97e5-081e-44fc-a759-9a1ae81de41c">EvtIoTargetQueryRemove</a> callback function from the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">Toaster</a> sample driver. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
ToastMon_EvtIoTargetQueryRemove(
    WDFIOTARGET IoTarget
)
{
    PTARGET_DEVICE_INFO  targetDeviceInfo = NULL;
    //
    // Get the I/O target object's context.
    //
    targetDeviceInfo = GetTargetDeviceInfo(IoTarget);
    //
    // Ensure that the I/O target's work item
    // has been processed before closing the target.
    //
    WdfWorkItemFlush(targetDeviceInfo-&gt;WorkItem);
    WdfIoTargetCloseForQueryRemove(IoTarget);

    return STATUS_SUCCESS;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a>
 

 

