---
UID: NF:wdffdo.WdfFdoQueryForInterface
title: WdfFdoQueryForInterface function
author: windows-driver-content
description: The WdfFdoQueryForInterface method obtains access to another driver's GUID-identified interface.
old-location: wdf\wdffdoqueryforinterface.htm
old-project: wdf
ms.assetid: 12bbc77b-c1cd-4899-aff2-e18e0d58b6b9
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , DFDeviceObjectFdoPdoRef_949fcc50-3604-4970-9516-666da06e3c9e.xml, F, I, Q, W, WdfFdoQueryForInterface, WdfFdoQueryForInterface method, a, c, d, e, f, kmdf.wdffdoqueryforinterface, n, o, r, t, u, wdf.wdffdoqueryforinterface, wdffdo/WdfFdoQueryForInterface, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
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
-	WdfFdoQueryForInterface
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# WdfFdoQueryForInterface function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoQueryForInterface</b> method obtains access to another driver's GUID-identified interface.


## -syntax


````
NTSTATUS WdfFdoQueryForInterface(
  _In_     WDFDEVICE  Device,
  _In_     LPCGUID    InterfaceType,
  _Out_    PINTERFACE Interface,
  _In_     USHORT     Size,
  _In_     USHORT     Version,
  _In_opt_ PVOID      InterfaceSpecificData
);
````


## -parameters




### -param Fdo

TBD


### -param InterfaceType [in]

A pointer to a GUID that identifies the interface.


### -param Interface [out]

A pointer to a driver-allocated structure that receives the requested interface. This structure is defined by the driver that exports the requested interface and must begin with an <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure.


### -param Size [in]

The size, in bytes, of the driver-allocated structure that represents the requested interface.


### -param Version [in]

The version number of the requested interface. The format of this value is defined by the driver that exports the requested interface.


### -param InterfaceSpecificData [in, optional]

Additional interface-specific information. This parameter is optional and can be <b>NULL</b>.


#### - Device [in]

A handle to a framework device object.


## -returns



If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:

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
The device object is invalid or if the <i>Device</i>, <i>InterfaceType</i>, or <i>Interface</i> parameter is <b>NULL</b>. 


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate a request to send to another driver. 

</td>
</tr>
</table>
 

The method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



Your driver can call <b>WdfFdoQueryForInterface</b> to obtain access to a driver-defined interface that was created by a driver that is in the same driver stack that your driver is in. To access a driver-defined interface that was created by a driver that is in a different driver stack, your driver must call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetqueryforinterface.md">WdfIoTargetQueryForInterface</a>.

Framework-based drivers define interfaces by calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>. 

For more information about <b>WdfFdoQueryForInterface</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.


#### Examples

The following code example is from the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">Toaster</a> sample function driver. This example obtains access to an interface that the toaster sample bus driver defines.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>status = WdfFdoQueryForInterface(
                                 Device,
                                 &amp;GUID_TOASTER_INTERFACE_STANDARD,
                                 (PINTERFACE) &amp;fdoData-&gt;BusInterface, // Object context space
                                 sizeof(TOASTER_INTERFACE_STANDARD),
                                 1,
                                 NULL
                                 );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetqueryforinterface.md">WdfIoTargetQueryForInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoQueryForInterface method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

