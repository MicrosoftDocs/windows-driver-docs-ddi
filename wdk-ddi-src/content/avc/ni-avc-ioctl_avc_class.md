---
UID: NI:avc.IOCTL_AVC_CLASS
title: IOCTL_AVC_CLASS
author: windows-driver-content
description: The IOCTL_AVC_CLASS I/O control code is supported only from kernel mode, using the IRP_MJ_INTERNAL_DEVICE_CONTROL dispatch.Avc.sys supports two device interfaces, depending upon the type of instance (peer or virtual).
old-location: stream\ioctl_avc_class.htm
old-project: stream
ms.assetid: 033069b8-98e5-4302-ae4e-71f9249533ff
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_AVC_CLASS, IOCTL_AVC_CLASS control code [Streaming Media Devices], avc/IOCTL_AVC_CLASS, avcref_720c03f6-d568-4ebe-8bd8-295fd8a6c222.xml, stream.ioctl_avc_class
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	avc.h
apiname:
-	IOCTL_AVC_CLASS
product: Windows
targetos: Windows
req.typenames: AVC_FUNCTION
---

# IOCTL_AVC_CLASS IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

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

For more information about IRPs and IOCTLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546847">Handling IRPs</a>.




## -ioctlparameters




### -input-buffer



<text></text>




### -input-buffer-length



<text></text>




### -output-buffer



<text></text>




### -output-buffer-length



<text></text>




### -in-out-buffer

<b>Parameters-&gt;Others.Argument1</b> points to either an AVC_COMMAND_IRB structure or AVC_MULTIFUNC_IRB structure. Both structures contain an AVC_IRB structure as a header, as illustrated in the following example:

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

<b>Parameters-&gt;Others.Argument1</b> points to the same AVC_COMMAND_IRB or AVC_MULTIFUNC_IRB structure that was passed as input. As part of completing the function, the subunit driver fills in certain submembers of the union within the structure with information for the driver. The returned information is documented with each request.


### -inout-buffer-length



<text></text>




### -status-block

The information the AV/C protocol driver returns in the I/O Status Block (Irp-&gt;IoStatus.Status) is documented with each request.


## -remarks



Most AV/C functions must be called IRQL = PASSIVE_LEVEL. A few may be called at IRQL &lt;= DISPATCH_LEVEL. The respective IRQL is documented in each AV/C function.




## -see-also

<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>



<a href="..\avc\ni-avc-ioctl_avc_remove_virtual_subunit_info.md">IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO</a>



<a href="..\avc\ni-avc-ioctl_avc_update_virtual_subunit_info.md">IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO</a>



<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>



<a href="..\avc\ns-avc-_avc_irb.md">AVC_IRB</a>



<a href="..\avc\ns-avc-_avc_command_irb.md">AVC_COMMAND_IRB</a>



<a href="..\avc\ni-avc-ioctl_avc_bus_reset.md">IOCTL_AVC_BUS_RESET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IOCTL_AVC_CLASS control code%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

