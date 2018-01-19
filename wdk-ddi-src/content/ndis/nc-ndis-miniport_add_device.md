---
UID: NC:ndis.MINIPORT_ADD_DEVICE
title: MINIPORT_ADD_DEVICE
author: windows-driver-content
description: The MiniportAddDevice function enables a miniport driver to establish a context area for an added device.
old-location: netvista\miniportadddevice.htm
old-project: netvista
ms.assetid: 50e04b5a-e430-484c-aabb-cc7b9ecb53b0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportAddDevice
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_ADD_DEVICE callback



## -description
The 
   <i>MiniportAddDevice</i> function enables a miniport driver to establish a context area
   for an added device.



## -prototype

````
MINIPORT_ADD_DEVICE MiniportAddDevice;

NDIS_STATUS MiniportAddDevice(
  _In_ NDIS_HANDLE NdisMiniportHandle,
  _In_ NDIS_HANDLE MiniportDriverContext
)
{ ... }
````


## -parameters

### -param NdisMiniportHandle [in]

An NDIS handle that identifies the miniport adapter that the Plug and Play (PnP) manager is
     adding. NDIS also passes this handle to the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


### -param MiniportDriverContext [in]

A handle to a driver-allocated context area where the driver maintains state and configuration
     information. The miniport driver passed this context area to the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> function.


## -returns
<i>MiniportAddDevice</i> returns one of the following values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The miniport driver successfully allocated the resources that it requires to add the
       device.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>The miniport driver failed to allocate the required resources.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
<a href="..\ndis\nc-ndis-miniport_add_device.md">MiniportAddDevice</a> failed for reasons other than insufficient
       resources.

 

If 
     <i>MiniportAddDevice</i> fails, NDIS will not call the <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function
     to initialize the miniport adapter.


## -remarks
The 
    <i>MiniportAddDevice</i> function is an optional function. Miniport drivers that
    support MSI-X should specify an entry point for this function in the 
    <a href="..\ndis\ns-ndis-_ndis_miniport_pnp_characteristics.md">
    NDIS_MINIPORT_PNP_CHARACTERISTICS</a> structure.

<i>MiniportAddDevice</i> can allocate a context area for handling 
    <a href="https://msdn.microsoft.com/f43dc60e-de88-4af0-ad83-3ce3a414d880">
    IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a> I/O request packets (IRPs) that the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff559452(d=robot)">
    MiniportFilterResourceRequirements</a> function handles. Miniport drivers specify the context area by
    initializing an 
    <a href="..\ndis\ns-ndis-_ndis_miniport_add_device_registration_attributes.md">
    NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a> structure and then calling the 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
    NdisMSetMiniportAttributes</a> function. NDIS later provides this context handle to the 
    <a href="..\ndis\nc-ndis-miniport_remove_device.md">MiniportRemoveDevice</a>, 
    <i>
    MiniportFilterResourceRequirements</i>, 
    <a href="..\ndis\nc-ndis-miniport_pnp_irp.md">MiniportStartDevice</a>, and 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> functions.
    For 
    <i>MiniportInitializeEx</i>, the context handle is passed in the 
    <b>MiniportAddDeviceContext</b> member of the 
    <a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">
    NDIS_MINIPORT_INIT_PARAMETERS</a> structure that the 
    <i>MiniportInitParameters</i> parameter points to.

If the miniport driver fails the 
    <i>MiniportAddDevice</i> call after it allocated the context area, the driver must
    free the context area before returning from 
    <i>MiniportAddDevice</i>.

Miniport drivers should use a different context area for the 
    <b>MiniportAddDeviceContext</b> member of the <a href="..\ndis\ns-ndis-_ndis_miniport_add_device_registration_attributes.md">NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a> structure
    and the 
    <b>MiniportAdapterContext</b> member of the <a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">NDIS_MINIPORT_INIT_PARAMETERS</a> structure. Separate context
    areas will ensure that information in the context area is not reinitialized, which might occur in the 
    <i>MiniportInitializeEx</i> function if the miniport adapter is halted and
    reinitialized.

When the PnP manager requests that NDIS remove the device, NDIS calls the 
    <a href="..\ndis\nc-ndis-miniport_remove_device.md">MiniportRemoveDevice</a> function to
    undo the operations that 
    <i>MiniportAddDevice</i> performed.

NDIS calls 
    <i>MiniportAddDevice</i> at IRQL = PASSIVE_LEVEL.

To define a <i>MiniportAddDevice</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportAddDevice</i> function that is named "MyAddDevice", use the <b>MINIPORT_ADD_DEVICE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_ADD_DEVICE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_ADD_DEVICE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/f43dc60e-de88-4af0-ad83-3ce3a414d880">
   IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559452(d=robot)">
   MiniportFilterResourceRequirements</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_remove_device.md">MiniportRemoveDevice</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_pnp_irp.md">MiniportStartDevice</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_add_device_registration_attributes.md">
   NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">NDIS_MINIPORT_INIT_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_pnp_characteristics.md">
   NDIS_MINIPORT_PNP_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_ADD_DEVICE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

