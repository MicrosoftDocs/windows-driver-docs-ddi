---
UID: NF:wdffdo.WdfFdoAddStaticChild
title: WdfFdoAddStaticChild function (wdffdo.h)
description: The WdfFdoAddStaticChild method adds a specified device to a function driver's list of child devices that have been identified by static enumeration.
old-location: wdf\wdffdoaddstaticchild.htm
tech.root: wdf
ms.assetid: 3e1c4469-7ae2-4ac8-8dfe-ff8c4cae3d20
ms.date: 02/26/2018
keywords: ["WdfFdoAddStaticChild function"]
ms.keywords: DFDeviceObjectFdoPdoRef_8374594a-a113-43da-a442-bd51e65ca53a.xml, WdfFdoAddStaticChild, WdfFdoAddStaticChild method, kmdf.wdffdoaddstaticchild, wdf.wdffdoaddstaticchild, wdffdo/WdfFdoAddStaticChild
f1_keywords:
 - "wdffdo/WdfFdoAddStaticChild"
 - "WdfFdoAddStaticChild"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfFdoAddStaticChild
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfFdoAddStaticChild function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

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
 

The method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



Drivers that use static bus enumeration can call <b>WdfFdoAddStaticChild</b>. For more information about static child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

If <b>WdfFdoAddStaticChild</b> returns an NTSTATUS value that <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a> evaluates as <b>FALSE</b>, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a> to delete the framework device object that represents the child device. The driver must not delete the framework device object after <b>WdfFdoAddStaticChild</b> returns STATUS_SUCCESS.


#### Examples

The following code example creates a framework device object that represents a new child device and adds the child device to the parent device's list of children. For the complete code example, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">KbFiltr</a> sample driver.

```cpp
NTSTATUS  status;
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
                         &pDeviceInit,
                         &pdoAttributes,
                         &hChild
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
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitallocate">WdfPdoInitAllocate</a>
 

 

