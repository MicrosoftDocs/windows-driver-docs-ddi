---
UID: NF:wdfiotarget.WdfIoTargetQueryForInterface
title: WdfIoTargetQueryForInterface function
author: windows-driver-content
description: The WdfIoTargetQueryForInterface method obtains access to the GUID-identified, driver-defined interface of a remote I/O target.
old-location: wdf\wdfiotargetqueryforinterface.htm
tech.root: wdf
ms.assetid: 213d0ee8-96f1-4927-be87-1b504b3f3478
ms.date: 02/26/2018
ms.keywords: DFIOTargetRef_ed9f676e-903e-4a93-ad0a-80c428ed8230.xml, WdfIoTargetQueryForInterface, WdfIoTargetQueryForInterface method, kmdf.wdfiotargetqueryforinterface, wdf.wdfiotargetqueryforinterface, wdfiotarget/WdfIoTargetQueryForInterface
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
api_name:
-	WdfIoTargetQueryForInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetQueryForInterface function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoTargetQueryForInterface</b> method obtains access to the GUID-identified, driver-defined interface of a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets">remote I/O target</a>.


## -parameters




### -param IoTarget [in]

A handle to a remote I/O target object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>.


### -param InterfaceType [in]

A pointer to a GUID that identifies the interface.


### -param Interface [out]

A pointer to a driver-allocated structure that receives the requested interface. This structure is defined by the driver that exports the requested interface and must begin with an <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure.


### -param Size [in]

The size, in bytes, of the driver-allocated structure that <i>Interface</i> points to.


### -param Version [in]

The version number of the requested interface. The driver that exports the requested interface defines the format of this value.


### -param InterfaceSpecificData [in, optional]

Additional interface-specific information. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>WdfIoTargetQueryForInterface</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>IoTarget</i>, <i>InterfaceType</i>, or <i>Interface</i> parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
 the framework could not allocate a request to send to another driver.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Your driver can call <b>WdfIoTargetQueryForInterface</b> to obtain access to a driver-defined interface that was created by a driver in a different driver stack. To access a driver-defined interface that was created by a driver that is in the same driver stack as your driver, your driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547289">WdfFdoQueryForInterface</a>.

Framework-based drivers define interfaces by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545870">WdfDeviceAddQueryInterface</a>. For more information about driver-defined interfaces, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.


#### Examples

The following code example attempts to gain access to a specified remote I/O target's interface. GUID_RAWPDO_INTERFACE_STANDARD is the GUID that identifies the interface.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS status;
RAWPDO_INTERFACE_STANDARD busInterface;

status = WdfIoTargetQueryForInterface(
                                      IoTarget,
                                      &amp;GUID_RAWPDO_INTERFACE_STANDARD,
                                      (PINTERFACE) &amp;busInterface,
                                      sizeof(RAWPDO_INTERFACE_STANDARD),
                                      1,
                                      NULL
                                      );
if (!NT_SUCCESS (status)){
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545870">WdfDeviceAddQueryInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547289">WdfFdoQueryForInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>
 

 

