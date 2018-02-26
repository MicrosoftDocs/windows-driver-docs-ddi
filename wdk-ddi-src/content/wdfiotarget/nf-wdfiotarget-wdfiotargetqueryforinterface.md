---
UID: NF:wdfiotarget.WdfIoTargetQueryForInterface
title: WdfIoTargetQueryForInterface function
author: windows-driver-content
description: The WdfIoTargetQueryForInterface method obtains access to the GUID-identified, driver-defined interface of a remote I/O target.
old-location: wdf\wdfiotargetqueryforinterface.htm
old-project: wdf
ms.assetid: 213d0ee8-96f1-4927-be87-1b504b3f3478
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , DFIOTargetRef_ed9f676e-903e-4a93-ad0a-80c428ed8230.xml, F, I, Q, T, W, WdfIoTargetQueryForInterface, WdfIoTargetQueryForInterface method, a, c, d, e, f, g, kmdf.wdfiotargetqueryforinterface, n, o, r, t, u, wdf.wdfiotargetqueryforinterface, wdfiotarget/WdfIoTargetQueryForInterface, y"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfIoTargetQueryForInterface
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WdfIoTargetQueryForInterface function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoTargetQueryForInterface</b> method obtains access to the GUID-identified, driver-defined interface of a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets">remote I/O target</a>.


## -syntax


````
NTSTATUS WdfIoTargetQueryForInterface(
  _In_     WDFIOTARGET IoTarget,
  _In_     LPCGUID     InterfaceType,
  _Out_    PINTERFACE  Interface,
  _In_     USHORT      Size,
  _In_     USHORT      Version,
  _In_opt_ PVOID       InterfaceSpecificData
);
````


## -parameters




### -param IoTarget [in]

A handle to a remote I/O target object that was obtained from a previous call to <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>.


### -param InterfaceType [in]

A pointer to a GUID that identifies the interface.


### -param Interface [out]

A pointer to a driver-allocated structure that receives the requested interface. This structure is defined by the driver that exports the requested interface and must begin with an <a href="..\miniport\ns-miniport-_interface.md">INTERFACE</a> structure.


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



Your driver can call <b>WdfIoTargetQueryForInterface</b> to obtain access to a driver-defined interface that was created by a driver in a different driver stack. To access a driver-defined interface that was created by a driver that is in the same driver stack as your driver, your driver must call <a href="..\wdffdo\nf-wdffdo-wdffdoqueryforinterface.md">WdfFdoQueryForInterface</a>.

Framework-based drivers define interfaces by calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>. For more information about driver-defined interfaces, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.


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

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>



<a href="..\wdffdo\nf-wdffdo-wdffdoqueryforinterface.md">WdfFdoQueryForInterface</a>



<a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>



<a href="..\miniport\ns-miniport-_interface.md">INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetQueryForInterface method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

