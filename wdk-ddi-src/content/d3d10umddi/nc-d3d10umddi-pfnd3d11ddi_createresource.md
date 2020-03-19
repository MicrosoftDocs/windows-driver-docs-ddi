---
UID: NC:d3d10umddi.PFND3D11DDI_CREATERESOURCE
title: PFND3D11DDI_CREATERESOURCE (d3d10umddi.h)
description: Creates a resource.
old-location: display\createresource_d3d11_.htm
ms.assetid: 2dff9d2e-c497-422f-824b-a7101904fd67
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_CREATERESOURCE callback function"]
ms.keywords: CreateResource, CreateResource callback function [Display Devices], PFND3D11DDI_CREATERESOURCE, PFND3D11DDI_CREATERESOURCE callback, UserModeDisplayDriverDx11_Functions_3ac053d0-82dc-4bdf-af15-258af82c568b.xml, d3d10umddi/CreateResource, display.createresource_d3d11_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateResource(D3D11) is supported beginning with the Windows 7 operating system.
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/CreateResource"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CreateResource
product:
 - Windows
---

# PFND3D11DDI_CREATERESOURCE callback function

## -description

Creates a resource.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateResource* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a> structure that describes the parameters that the user-mode display driver uses to create a resource.

### -param Arg3

*hResource* [in]

A handle to the driver's private data for the resource.

### -param Arg4

*hRTResource* [in]

A handle to the resource that the driver will use when it calls back into the Direct3D runtime.

## -remarks



The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 


The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The driver can also pass DXGI_DDI_ERR_UNSUPPORTED in a call to <b>pfnSetErrorCb</b>. For more information about passing DXGI_DDI_ERR_UNSUPPORTED, see the Remarks section of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> reference page. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyresource">DestroyResource(D3D10)</a> function to destroy the handle that the <i>hResource</i> parameter specifies.

The runtime validates all parameters against the parameters that an application sent to create the resource. Therefore, the driver should not receive invalid combinations.

If the application does not require the contents of the resource to persist across presentations, the runtime sets the D3D10_DDI_RESOURCE_MISC_DISCARD_ON_PRESENT flag of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_resource_misc_flag">D3D10_DDI_RESOURCE_MISC_FLAG</a> enumeration in the <b>MiscFlags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a> structure that the <i>pCreateResource</i> parameter points to. Presentation occurs when the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> (with the <b>Present</b> flag set in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt_flags">DXGI_DDI_ARG_BLT_FLAGS</a> structure) function is called. The runtime uses the D3D10_DDI_RESOURCE_MISC_DISCARD_ON_PRESENT flag to create swap-chain back buffers when an application uses the DXGI_SWAP_EFFECT_DISCARD value to request swap chains. 

<h3><a id="Creating_a_Stereo_Back_Buffer"></a><a id="creating_a_stereo_back_buffer"></a><a id="CREATING_A_STEREO_BACK_BUFFER"></a>Creating a Stereo Back Buffer</h3>
Starting in Windows 8, if the driver must create a stereo back buffer, it must set members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a> structure pointed to by <i>pCreateResource</i> as follows:

<ol>
<li>Set the <b>ArraySize</b> member to a value of 2.</li>
<li>Set the D3D10_DDI_BIND_PRESENT flag value in the <b>BindFlags</b> member.</li>
</ol>
Additionally, to support stereo presentation, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> function must allow any values for the <b>DstSubresource</b> and <b>SrcSubresource</b> members of  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt">DXGI_DDI_ARG_BLT</a> structure that are within the range of the source and destination resources.

<h3><a id="Restrictions_on_input_values"></a><a id="restrictions_on_input_values"></a><a id="RESTRICTIONS_ON_INPUT_VALUES"></a>Restrictions on input values</h3>
For Windows Display Driver Model (WDDM) 1.3 and later drivers, the Microsoft Direct3D runtime supplies a restricted set of input values used by this function. For a list of all restricted values, see [Direct3D rendering performance improvements](https://docs.microsoft.com/windows-hardware/drivers/display/direct3d-rendering-performance-improvements).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivateresourcesize">CalcPrivateResourceSize(D3D11)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_resource_misc_flag">D3D10_DDI_RESOURCE_MISC_FLAG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt">DXGI_DDI_ARG_BLT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt_flags">DXGI_DDI_ARG_BLT_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyresource">DestroyResource(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

