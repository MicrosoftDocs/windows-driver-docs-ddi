---
UID: NC:wdm.DRIVER_INITIALIZE
title: DRIVER_INITIALIZE
author: windows-driver-content
description: DriverEntry is the first routine called after a driver is loaded, and is responsible for initializing the driver.
old-location: kernel\driverentry.htm
old-project: kernel
ms.assetid: b8c14a2d-a2e6-4ed1-9445-3259ec570076
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.driverentry, DriverEntry routine [Kernel-Mode Driver Architecture], DriverEntry, DRIVER_INITIALIZE, DRIVER_INITIALIZE, wdm/DriverEntry, DrvrRtns_dc503a23-7c31-421d-ac7b-ff6f4651e44e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Mcd.h, Ntddk.h, Ntifs.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	DriverEntry
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# DRIVER_INITIALIZE callback


## -description


<b>DriverEntry</b> is the first routine called after a driver is loaded, and is responsible for initializing the driver.


## -prototype


````
DRIVER_INITIALIZE DriverEntry;

NTSTATUS DriverEntry(
  _In_ struct _DRIVER_OBJECT *DriverObject,
  _In_ PUNICODE_STRING       RegistryPath
)
{ ... }
````


## -parameters




#### - *DriverObject [in]

A pointer to a <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure. This is the driver's driver object.


#### - RegistryPath [in]

A pointer to a counted Unicode string specifying the path to the driver's registry key.


#### - DriverObject [in]

A pointer to a <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure. This is the driver's driver object.


## -returns


If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in Ntstatus.h.



## -remarks


The <i>DriverObject</i> parameter supplies the <b>DriverEntry</b> routine with a pointer to the driver's driver object, which is allocated by the I/O manager. The <b>DriverEntry</b> routine must fill in the driver object with entry points for the driver's standard routines.

The <i>DriverObject</i> pointer gives the driver access to <i>DriverObject-</i>&gt;<b>HardwareDatabase</b>, which points to a counted Unicode string that specifies a path to the registry's <b>\Registry\Machine\Hardware</b> tree.

The registry path string pointed to by <i>RegistryPath</i> is of the form <b>\Registry\Machine\System\CurrentControlSet\Services\<i>DriverName</i></b>. A driver can use this path to store driver-specific information; see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/overview-of-registry-trees-and-keys">Registry Keys for Drivers</a>. The <b>DriverEntry</b> routine should save a copy of the Unicode string, not the pointer, since the I/O manager frees the <i>RegistryPath</i> buffer after <b>DriverEntry</b> returns.

For more information about implementing a <b>DriverEntry</b> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566402">Writing a DriverEntry Routine</a>.

While it is possible to name this routine something other than <b>DriverEntry</b>, doing so is not recommended. The DDK-supplied build tools automatically inform the linker that the driver's entry point is called <b>DriverEntry</b>, so giving the routine another name requires you to modify the build tools. For more information about build tools, see <a href="https://msdn.microsoft.com/windows-drivers/develop/building_a_driver">Building a Driver</a>.



## -see-also

<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DRIVER_INITIALIZE routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

