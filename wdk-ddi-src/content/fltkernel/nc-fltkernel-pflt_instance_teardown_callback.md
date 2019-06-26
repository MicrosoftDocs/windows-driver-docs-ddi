---
UID: NC:fltkernel.PFLT_INSTANCE_TEARDOWN_CALLBACK
title: PFLT_INSTANCE_TEARDOWN_CALLBACK (fltkernel.h)
description: A minifilter driver can register two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK as the minifilter driver's InstanceTeardownStartCallback and InstanceTeardownCompleteCallback routines.
old-location: ifsk\pflt_instance_teardown_callback.htm
tech.root: ifsk
ms.assetid: d2f87c47-7f26-4c22-a5b8-2be8f309d1ba
ms.date: 03/29/2018
ms.keywords: FltCallbacks_2bec09ed-3009-465c-842b-67e0cd7d734f.xml, PFLT_INSTANCE_TEARDOWN_CALLBACK, PFLT_INSTANCE_TEARDOWN_CALLBACK function pointer [Installable File System Drivers], fltkernel/PFLT_INSTANCE_TEARDOWN_CALLBACK, ifsk.pflt_instance_teardown_callback
ms.topic: callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- fltkernel.h
api_name:
- PFLT_INSTANCE_TEARDOWN_CALLBACK
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# PFLT_INSTANCE_TEARDOWN_CALLBACK callback


## -description


A minifilter driver can register two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK as the minifilter driver's <i>InstanceTeardownStartCallback</i> and <i>InstanceTeardownCompleteCallback</i> routines.


## -parameters




### -param FltObjects [in]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure that contains opaque pointers for the objects related to the current I/O operation.


### -param Reason [in]

Flag that indicates why the minifilter driver instance is being torn down. One of the following:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLTFL_INSTANCE_TEARDOWN_FILTER_UNLOAD

</td>
<td>
The minifilter driver is being unloaded.

</td>
</tr>
<tr>
<td>
FLTFL_INSTANCE_TEARDOWN_INTERNAL_ERROR

</td>
<td>
An error, such as a memory allocation failure, occurred during instance setup.

</td>
</tr>
<tr>
<td>
FLTFL_INSTANCE_TEARDOWN_MANDATORY_FILTER_UNLOAD

</td>
<td>
The minifilter driver is being unloaded.

</td>
</tr>
<tr>
<td>
FLTFL_INSTANCE_TEARDOWN_MANUAL

</td>
<td>
The instance is being detached because a user-mode application has called <a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterdetach">FilterDetach</a> or a kernel-mode component has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltdetachvolume">FltDetachVolume</a>.

</td>
</tr>
<tr>
<td>
FLTFL_INSTANCE_TEARDOWN_VOLUME_DISMOUNT

</td>
<td>
If set, the volume is being dismounted. (Or the volume has already been dismounted. Or the volume mount operation failed. Or the minifilter driver instance or the volume is being torn down. Or the file system unregistered itself as an active file system.)

</td>
</tr>
</table>
 


## -returns



None




## -remarks



When a minifilter driver registers itself by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine, it can register two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK as the minifilter driver's <i>InstanceTeardownStartCallback</i> and <i>InstanceTeardownCompleteCallback</i> routines.

To register these callback routines, the minifilter driver stores the addresses of the two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK in the <b>InstanceTeardownStartCallback</b> and <b>InstanceTeardownCompleteCallback</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a> structure that the minifilter driver passes as the <i>Registration</i> parameter of <b>FltRegisterFilter</b>.

The <i>InstanceTeardownStartCallback</i> and <i>InstanceTeardownCompleteCallback</i> routines are optional and can be <b>NULL</b>. If the minifilter driver specifies <b>NULL</b> for the <i>InstanceTeardownStartCallback</i> or <i>InstanceTeardownCompleteCallback</i> routine, the instance is still torn down.

The <i>InstanceTeardownStartCallback</i> routine is called when the filter manager starts tearing down a minifilter driver instance to allow the minifilter driver to complete any pended I/O operations and save state information.

The <i>InstanceTeardownStartCallback</i> routine must:

<ul>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcompletependedpreoperation">FltCompletePendedPreOperation</a> for each I/O operation that was pended in the minifilter driver's preoperation callback routine to complete the operation or return control of the operation to the filter manager.

</li>
<li>
Not pend any new I/O operations. If the minifilter driver uses a callback data queue, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcbdqdisable">FltCbdqDisable</a> to disable it.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcompletependedpostoperation">FltCompletePendedPostOperation</a> for each I/O operation that was pended in the minifilter driver's postoperation callback routine to return control of the operation to the filter manager.

</li>
</ul>
The <i>InstanceTeardownStartCallback</i> routine can optionally do the following to allow the minifilter driver to unload as quickly as possible:

<ul>
<li>
Close any opened files.

</li>
<li>
Ensure that worker threads perform only the minimum necessary to complete processing of outstanding work items.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo</a> to cancel any I/O operations that were initiated by the minifilter driver.

</li>
<li>
Stop queuing new work items.

</li>
</ul>
Once the minifilter driver's <i>InstanceTeardownStartCallback</i> routine is called, the minifilter driver's preoperation and postoperation callback routines are not called for any new I/O operations. However, they may be called for I/O operations that were started before instance teardown was initiated.

The <i>InstanceTeardownCompleteCallback</i> routine is called when the teardown process is complete to allow the minifilter driver to close open files and perform any other necessary cleanup processing.

The <i>InstanceTeardownCompleteCallback</i> routine must close any files that were opened by the minifilter driver.

The filter manager calls the minifilter driver's <i>InstanceTeardownCompleteCallback</i> routine only after all outstanding I/O operations have been completed or drained.

<b>Warning</b>: The <i>InstanceTeardownCompleteCallback</i> routine will not be called if any of the following conditions are true:

<ul>
<li>
There are outstanding pended I/O operations.

</li>
<li>
There are any outstanding I/O operations that were initiated by the minifilter driver.

</li>
</ul>
If the minifilter driver instance is being torn down because the minifilter driver is being unloaded, the unload operation appears to hang until the <i>InstanceTeardownCompleteCallback</i> routine returns. To debug these kinds of problems, you should enable the <a href="https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a> on your minifilter driver. The Filter Verifier <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/i-o-verification">I/O Verification</a> option can help identify possible causes, such as unreleased references, that would prevent the minifilter driver from unloading. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/development-and-testing-tools">Filter Verifier</a>.

Note that referencing the instance (by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltobjectreference">FltObjectReference</a>) does not prevent the <i>InstanceTeardownCompleteCallback</i> routine from being called.

The filter manager calls the <i>InstanceTeardownStartCallback</i> and <i>InstanceTeardownCompleteCallback</i> routines at IRQL PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterdetach">FilterDetach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcbdqdisable">FltCbdqDisable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcompletependedpostoperation">FltCompletePendedPostOperation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcompletependedpreoperation">FltCompletePendedPreOperation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltdetachvolume">FltDetachVolume</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_instance_query_teardown_callback">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_instance_setup_callback">PFLT_INSTANCE_SETUP_CALLBACK</a>
 

 

