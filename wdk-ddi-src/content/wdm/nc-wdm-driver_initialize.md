---
UID: NC:wdm.DRIVER_INITIALIZE
title: DRIVER_INITIALIZE (wdm.h)
description: DriverEntry is the first routine called after a driver is loaded, and is responsible for initializing the driver.
old-location: kernel\driverentry.htm
tech.root: kernel
ms.assetid: b8c14a2d-a2e6-4ed1-9445-3259ec570076
ms.date: 04/30/2018
ms.keywords: DRIVER_INITIALIZE, DriverEntry, DriverEntry routine [Kernel-Mode Driver Architecture], DrvrRtns_dc503a23-7c31-421d-ac7b-ff6f4651e44e.xml, kernel.driverentry, wdm/DriverEntry
f1_keywords:
 - "wdm/DriverEntry"
req.header: wdm.h
req.include-header: Mcd.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- DriverEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# DRIVER_INITIALIZE callback function


## -description


<b>DriverEntry</b> is the first routine called after a driver is loaded, and is responsible for initializing the driver.


## -parameters




### -param *DriverObject [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a> structure. This is the driver's driver object.


### -param RegistryPath [in]

A pointer to a counted Unicode string specifying the path to the driver's registry key.


## -returns



If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in Ntstatus.h.




## -remarks



The <i>DriverObject</i> parameter supplies the <b>DriverEntry</b> routine with a pointer to the driver's driver object, which is allocated by the I/O manager. The <b>DriverEntry</b> routine must fill in the driver object with entry points for the driver's standard routines.

The <i>DriverObject</i> pointer gives the driver access to <i>DriverObject-</i>><b>HardwareDatabase</b>, which points to a counted Unicode string that specifies a path to the registry's <b>\Registry\Machine\Hardware</b> tree.

The registry path string pointed to by <i>RegistryPath</i> is of the form <b>\Registry\Machine\System\CurrentControlSet\Services\<i>DriverName</i></b>. A driver can use this path to store driver-specific information; see <a href="https://docs.microsoft.com/windows-hardware/drivers/install/overview-of-registry-trees-and-keys">Registry Keys for Drivers</a>. The <b>DriverEntry</b> routine should save a copy of the Unicode string, not the pointer, since the I/O manager frees the <i>RegistryPath</i> buffer after <b>DriverEntry</b> returns.

For more information about implementing a <b>DriverEntry</b> routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-driverentry-routine">Writing a DriverEntry Routine</a>.

While it is possible to name this routine something other than <b>DriverEntry</b>, doing so is not recommended. The DDK-supplied build tools automatically inform the linker that the driver's entry point is called <b>DriverEntry</b>, so giving the routine another name requires you to modify the build tools. For more information about build tools, see <a href="https://docs.microsoft.com/windows-hardware/drivers/develop/building-a-driver">Building a Driver</a>.


#### Examples

To define a <b>DriverEntry</b> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

To define a <b>DriverEntry</b> callback routine, use the DRIVER_INITIALIZE type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DRIVER_INITIALIZE DriverEntry;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
_Use_decl_annotations_
NTSTATUS 
  DriverEntry( 
    struct _DRIVER_OBJECT  *DriverObject,
    PUNICODE_STRING  RegistryPath 
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The DRIVER_INITIALIZE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the DRIVER_INITIALIZE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>
 

 

