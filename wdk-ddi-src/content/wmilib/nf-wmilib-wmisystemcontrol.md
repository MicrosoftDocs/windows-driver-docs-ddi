---
UID: NF:wmilib.WmiSystemControl
title: WmiSystemControl function (wmilib.h)
description: The WmiSystemControl routine is a dispatch routine for drivers that use WMI library support routines to handle WMI IRPs.
old-location: kernel\wmisystemcontrol.htm
tech.root: kernel
ms.assetid: 6226e75e-b744-46cd-b14b-e93ece1c2f61
ms.date: 04/30/2018
keywords: ["WmiSystemControl function"]
ms.keywords: WmiSystemControl, WmiSystemControl routine [Kernel-Mode Driver Architecture], k902_7bd87d12-7e45-4dd1-a78b-6389c6894ea4.xml, kernel.wmisystemcontrol, wmilib/WmiSystemControl
f1_keywords:
 - "wmilib/WmiSystemControl"
 - "WmiSystemControl"
req.header: wmilib.h
req.include-header: Wmilib.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: WmiComplete
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wmilib.lib
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wmilib.lib
- Wmilib.dll
api_name:
- WmiSystemControl
targetos: Windows
req.typenames: 
---

# WmiSystemControl function


## -description


The <b>WmiSystemControl</b> routine is a dispatch routine for drivers that use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">WMI library support routines</a> to handle WMI IRPs.


## -parameters




### -param WmiLibInfo [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/ns-wmilib-_wmilib_context">WMILIB_CONTEXT</a> structure that contains registration information for a driver's data blocks and event blocks and defines entry points for the driver's WMI library callback routines. 


### -param DeviceObject [in]

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>. 


### -param Irp [in, out]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>.


### -param IrpDisposition [out]


      A pointer to an enumeration value of type <b>SYSCTL_IRP_DISPOSITION</b> that indicates how the IRP was handled. <b>WmiSystemControl</b> always sets this value, even when it returns a non-success NTSTATUS code.

<b>SYSCTL_IRP_DISPOSITION</b> is an enumeration in Wmilib.h and contains the following values:





#### IrpProcessed

The IRP was processed and possibly completed. If the driver's <i>DpWmi</i>Xxx routine called by <b>WmiSystemControl</b> did not complete the IRP, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nf-wmilib-wmicompleterequest">WmiCompleteRequest</a> to complete the IRP after <b>WmiSystemControl</b> returns.



#### IrpNotCompleted

The IRP was processed but not completed, either because WMI detected an error and set up the IRP with an appropriate error code, or processed an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo">IRP_MN_REGINFO</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo-ex">IRP_MN_REGINFO_EX</a> request. The driver must complete the IRP by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>.



#### IrpNotWmi

The IRP is not a WMI request (that is, WMI does not recognize the IRP's minor code). If the driver handles <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-system-control">IRP_MJ_SYSTEM_CONTROL</a> requests with this <b>IRP_MN_<i>XXX</i></b>, it should handle the IRP; otherwise, the driver should forward the IRP to the next lower driver. If the driver is the lowest-level driver, then it must complete the IRP.



#### IrpForward

The IRP is targeted to another device object (that is, the device object pointer at <b>Parameters.WMI.ProviderId</b> in the IRP does not match the pointer passed by the driver in its call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiregistrationcontrol">IoWMIRegistrationControl</a>). The driver must forward the IRP to the next lower driver. If the driver is the lowest-level driver, then it must complete the IRP.


## -returns



<b>WmiSystemControl</b> returns STATUS_SUCCESS or one of the following error codes:




## -remarks



When a driver receives an <b>IRP_MJ_SYSTEM_CONTROL</b> request with a WMI IRP minor code, it calls <b>WmiSystemControl</b> with a pointer to the driver's <b>WMILIB_CONTEXT</b> structure, a pointer to its device object, and a pointer to the IRP. The <b>WMILIB_CONTEXT</b> structure contains registration information for the driver's data blocks and event blocks and defines entry points for its WMI library callback routines.

<b>WmiSystemControl</b> confirms that the IRP is a WMI request and determines whether the block specified by the request is valid for the driver. If so, it processes the IRP by calling the appropriate <i>DpWmi</i>Xxx entry point in the driver's <b>WMILIB_CONTEXT</b> structure. WMI is running at IRQL PASSIVE_LEVEL when it calls the driver's <i>DpWmi</i>Xxx routine.

A driver must be running at IRQL PASSIVE_LEVEL when it forwards an <b>IRP_MJ_SYSTEM_CONTROL</b> request to the next-lower driver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nc-wmilib-wmi_execute_method_callback">DpWmiExecuteMethod</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nc-wmilib-wmi_function_control_callback">DpWmiFunctionControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nc-wmilib-wmi_query_datablock_callback">DpWmiQueryDataBlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nc-wmilib-wmi_query_reginfo_callback">DpWmiQueryReginfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nc-wmilib-wmi_set_datablock_callback">DpWmiSetDataBlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nc-wmilib-wmi_set_dataitem_callback">DpWmiSetDataItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-system-control">IRP_MJ_SYSTEM_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo-ex">IRP_MN_REGINFO_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/ns-wmilib-_wmilib_context">WMILIB_CONTEXT</a>
 

 

