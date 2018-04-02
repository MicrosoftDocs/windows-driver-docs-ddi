---
UID: NF:wdffdo.WdfFdoAddStaticChild
title: WdfFdoAddStaticChild function
author: windows-driver-content
description: The WdfFdoAddStaticChild method adds a specified device to a function driver's list of child devices that have been identified by static enumeration.
old-location: wdf\wdffdoaddstaticchild.htm
old-project: wdf
ms.assetid: 3e1c4469-7ae2-4ac8-8dfe-ff8c4cae3d20
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_8374594a-a113-43da-a442-bd51e65ca53a.xml, WdfFdoAddStaticChild, WdfFdoAddStaticChild method, kmdf.wdffdoaddstaticchild, wdf.wdffdoaddstaticchild, wdffdo/WdfFdoAddStaticChild
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
req.ddi-compliance: AddPdoToStaticChildList, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfFdoAddStaticChild
product:
- Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# WdfFdoAddStaticChild function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoAddStaticChild</b> method adds a specified device to a function driver's list of child devices that have been identified by static enumeration.


## -parameters




### -param Fdo [in]

A handle to a framework device object that represents the parent device.


### -param Child [in]

A handle to a framework device object that represents the child device.


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
<i>Fdo</i> is not a handle to a function driver's device object.

</td>
</tr>
</table>
 

The method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



Drivers that use static bus enumeration can call <b>WdfFdoAddStaticChild</b>. For more information about static child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

If <b>WdfFdoAddStaticChild</b> returns an NTSTATUS value that <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a> evaluates as <b>FALSE</b>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548734">WdfObjectDelete</a> to delete the framework device object that represents the child device. The driver must not delete the framework device object after <b>WdfFdoAddStaticChild</b> returns STATUS_SUCCESS.


#### Examples

The following code example creates a framework device object that represents a new child device and adds the child device to the parent device's list of children. For the complete code example, see the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">KbFiltr</a> sample driver.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status;
PWDFDEVICE_INIT  pDeviceInit = NULL;
WDFDEVICE  hChild = NULL;
WDF_OBJECT_ATTRIBUTES  pdoAttributes;

pDeviceInit = WdfPdoInitAllocate(Device);
if (pDeviceInit == NULL) {
    status = STATUS_INSUFFICIENT_RESOURCES;
    goto Cleanup;
}
...
status = WdfDeviceCreate(
                         &amp;pDeviceInit,
                         &amp;pdoAttributes,
                         &amp;hChild
                         );
if (!NT_SUCCESS(status)) {
    WdfDeviceInitFree(pDeviceInit);
    pDeviceInit = NULL;
    goto Cleanup;
}
...
status = WdfFdoAddStaticChild(
                              Device,
                              hChild
                              );
if (!NT_SUCCESS(status)) {
    goto Cleanup;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545591">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548786">WdfPdoInitAllocate</a>
 

 

