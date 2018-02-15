---
UID: NC:wmilib.WMI_FUNCTION_CONTROL_CALLBACK
title: WMI_FUNCTION_CONTROL_CALLBACK
author: windows-driver-content
description: The DpWmiFunctionControl routine enables or disables notification of events, and enables or disables data collection for data blocks that the driver registered as expensive to collect. This routine is optional.
old-location: kernel\dpwmifunctioncontrol.htm
old-project: kernel
ms.assetid: c1480927-eefa-4078-a866-68dc1b7c5e9c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.dpwmifunctioncontrol, DpWmiFunctionControl, DpWmiFunctionControl callback function [Kernel-Mode Driver Architecture], DpWmiFunctionControl, WMI_FUNCTION_CONTROL_CALLBACK, WMI_FUNCTION_CONTROL_CALLBACK, wmilib/DpWmiFunctionControl, k903_d43ba720-8de2-411d-ae6c-3ba6b7bfe3ca.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wmilib.h
req.include-header: Wmilib.h
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
-	Wmilib.h
apiname:
-	DpWmiFunctionControl
product: Windows
targetos: Windows
req.typenames: WMI_CHANGER_PROBLEM_DEVICE_ERROR, *PWMI_CHANGER_PROBLEM_DEVICE_ERROR
req.product: Windows 10 or later.
---

# WMI_FUNCTION_CONTROL_CALLBACK callback


## -description


The <i>DpWmiFunctionControl</i> routine enables or disables notification of events, and enables or disables data collection for data blocks that the driver registered as expensive to collect. This routine is optional.


## -prototype


````
WMI_FUNCTION_CONTROL_CALLBACK DpWmiFunctionControl;

NTSTATUS DpWmiFunctionControl(
  _In_ PDEVICE_OBJECT          DeviceObject,
  _In_ PIRP                    Irp,
  _In_ ULONG                   GuidIndex,
  _In_ WMIENABLEDISABLECONTROL Function,
  _In_ BOOLEAN                 Enable
)
{ ... }
````


## -parameters




### -param DeviceObject [in]

Pointer to the driver's WDM <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure.


### -param Irp [in]

Pointer to the IRP.


### -param GuidIndex [in]

Specifies the data block by supplying a zero-based index into the list of GUIDs that the driver provided in the <a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a> structure it passed to <a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a>.


### -param Function [in]

Specifies what to enable or disable. <b>WmiEventControl</b> indicates an event, and <b>WmiDataBlockControl</b> indicates data collection for a block that was registered as expensive to collect (that is, a block for which the driver set WMIREG_FLAG_EXPENSIVE in <b>Flags</b> of the <a href="..\wmilib\ns-wmilib-_wmiguidreginfo.md">WMIGUIDREGINFO</a> structure used to register the block).


### -param Enable [in]

Specifies <b>TRUE</b> to enable the event or data collection, or <b>FALSE</b> to disable it.


## -returns



<i>DpWmiFunctionControl</i> returns STATUS_SUCCESS or an appropriate error status such as:




## -remarks



WMI calls a driver's <i>DpWmiFunctionControl</i> routine after the driver calls <a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a> in response to one of the following requests:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff550857">IRP_MN_ENABLE_COLLECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550848">IRP_MN_DISABLE_COLLECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550859">IRP_MN_ENABLE_EVENTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550851">IRP_MN_DISABLE_EVENTS</a>


If a driver implements a <i>DpWmiFunctionControl</i> routine, the driver must place the routine's address in the <b>WmiFunctionControl</b> member of the <a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a> structure that it passes to <a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a>. If a driver does not implement a <i>DpWmiFunctionControl</i> routine, it must set <b>WmiFunctionControl</b> to <b>NULL</b>. In the latter case, WMI returns STATUS_SUCCESS to the caller.

The driver is responsible for validating all input arguments. Specifically, the driver must do the following:

<ul>
<li>
Verify that the <i>GuidIndex</i> value is between zero and GuidCount-1, based on the <b>GuidCount</b> member of the <a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a> structure.

</li>
<li>
Verify that the driver has not flagged the specified data block for removal. If the driver recently specified the WMIREG_FLAG_REMOVE_GUID flag in a <a href="..\wmilib\ns-wmilib-_wmiguidreginfo.md">WMIGUIDREGINFO</a> structure that is contained in a <b>WMILIB_CONTEXT</b> structure, it is possible for an additional request to arrive before the removal occurs.

</li>
</ul>
It is unnecessary for the driver to check whether events or data collection are already enabled for a block, because WMI sends a single enable request when the first data consumer enables the block, and it sends a single disable request when the last data consumer disables the block. WMI will not call <i>DpWmiFunctionControl</i> to enable a block without an intervening call to disable it.

After enabling or disabling the event or data collection for the block, the driver calls <a href="..\wmilib\nf-wmilib-wmicompleterequest.md">WmiCompleteRequest</a> to complete the request.

This routine can be pageable.

For more information about implementing this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540741">Calling WmiSystemControl to Handle WMI IRPs</a>.




## -see-also

<a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550848">IRP_MN_DISABLE_COLLECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550851">IRP_MN_DISABLE_EVENTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550857">IRP_MN_ENABLE_COLLECTION</a>



<a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550859">IRP_MN_ENABLE_EVENTS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WMI_FUNCTION_CONTROL_CALLBACK callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

