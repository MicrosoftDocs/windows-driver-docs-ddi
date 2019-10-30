---
UID: NI:avc.IOCTL_AVC_CLASS
title: IOCTL_AVC_CLASS (avc.h)
description: The IOCTL_AVC_CLASS I/O control code is supported only from kernel mode, using the IRP_MJ_INTERNAL_DEVICE_CONTROL dispatch.Avc.sys supports two device interfaces, depending upon the type of instance (peer or virtual).
old-location: stream\ioctl_avc_class.htm
tech.root: stream
ms.assetid: 033069b8-98e5-4302-ae4e-71f9249533ff
ms.date: 04/23/2018
ms.keywords: IOCTL_AVC_CLASS, IOCTL_AVC_CLASS control, IOCTL_AVC_CLASS control code [Streaming Media Devices], avc/IOCTL_AVC_CLASS, avcref_720c03f6-d568-4ebe-8bd8-295fd8a6c222.xml, stream.ioctl_avc_class
ms.topic: ioctl
f1_keywords:
 - "avc/IOCTL_AVC_CLASS"
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- avc.h
api_name:
- IOCTL_AVC_CLASS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_AVC_CLASS IOCTL


## -description



The IOCTL_AVC_CLASS I/O control code is supported only from kernel mode, using the IRP_MJ_INTERNAL_DEVICE_CONTROL dispatch.

<i>Avc.sys</i> supports two device interfaces, depending upon the type of instance (peer or virtual). These interfaces define the functionality that the driver exposes for subunit drivers, other drivers, and applications. During initialization, <i>avc.sys</i> calls <b>IoRegisterDeviceInterface</b> with either GUID_AVC_CLASS (a peer, or nonvirtual instance) or GUID_VIRTUAL_AVC_CLASS (a virtual instance), then uses <b>IoSetDeviceInterfaceState</b> as appropriate for the started or stopped state of the driver.

Peer instances of <i>avc.sys</i> register the device interface identified by GUID_AVC_CLASS. This interface supports one I/O control code, IOCTL_AVC_CLASS, which in turn supports multiple function codes. Child drivers of peer <i>avc.sys</i> instances are guaranteed to have access to this interface through their parent device object.

Virtual instances of <i>avc.sys</i> register the device interface identified by GUID_VIRTUAL_AVC_CLASS. This interface supports four I/O control codes:

<ul>
<li>
IOCTL_AVC_CLASS

</li>
<li>
IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO

</li>
<li>
IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO

</li>
<li>
IOCTL_AVC_BUS_RESET

</li>
</ul>
The GUID_AVC_CLASS interface supports all IOCTL_AVC_CLASS function codes, although some have limitation on their use. However, the GUID_VIRTUAL_AVC_CLASS interface does not support all IOCTL_AVC_CLASS function codes. The reference page for each individual function code specifies whether it is supported for GUID_VIRTUAL_AVC_CLASS instances of <i>avc.sys</i>.

The IOCTL_AVC_CLASS function codes (and any restrictions) are described in each function code.

For more information about IRPs and IOCTLs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-irps">Handling IRPs</a>.




## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer

<b>Parameters->Others.Argument1</b> points to either an AVC_COMMAND_IRB structure or AVC_MULTIFUNC_IRB structure. Both structures contain an AVC_IRB structure as a header, as illustrated in the following example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _AVC_COMMAND_IRB {
  AVC_IRB  Common;
  .
  .
  .
} AVC_COMMAND_IRB, *PAVC_COMMAND_IRB;</pre>
</td>
</tr>
</table></span></div>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _AVC_MULTIFUNC_IRB {
  AVC_IRB  Common;
  .
  .
  .
} AVC_MULTIFUNC_IRB, *PAVC_MULTIFUNC_IRB;</pre>
</td>
</tr>
</table></span></div>
The AVC_IRB structure contains a single <b>Function</b> member. This member must be set to the desired function code from the AVC_FUNCTION enumeration.

The AVC_MULTIFUNC_IRB structure contains a union member that specifies the function I/O request block type-specific parameters for the function code. The parameters and their meanings are documented with each function code.

<b>Parameters->Others.Argument1</b> points to the same AVC_COMMAND_IRB or AVC_MULTIFUNC_IRB structure that was passed as input. As part of completing the function, the subunit driver fills in certain submembers of the union within the structure with information for the driver. The returned information is documented with each request.


### -inout-buffer-length








### -status-block

The information the AV/C protocol driver returns in the I/O Status Block (Irp->IoStatus.Status) is documented with each request.


## -remarks



Most AV/C functions must be called IRQL = PASSIVE_LEVEL. A few may be called at IRQL <= DISPATCH_LEVEL. The respective IRQL is documented in each AV/C function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_command_irb">AVC_COMMAND_IRB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ne-avc-_tagavc_function">AVC_FUNCTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_irb">AVC_IRB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_multifunc_irb">AVC_MULTIFUNC_IRB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ni-avc-ioctl_avc_bus_reset">IOCTL_AVC_BUS_RESET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ni-avc-ioctl_avc_remove_virtual_subunit_info">IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ni-avc-ioctl_avc_update_virtual_subunit_info">IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO</a>
 

 


