---
UID: NE:d3d10umddi.D3D10_DDI_RESOURCE_USAGE
title: D3D10_DDI_RESOURCE_USAGE
author: windows-driver-content
description: The D3D10_DDI_RESOURCE_USAGE enumeration type contains values that identify how a resource is used.
old-location: display\d3d10_ddi_resource_usage.htm
old-project: display
ms.assetid: f412b665-3489-4200-8fb8-7b6eb564ba98
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: D3D10_DDI_RESOURCE_USAGE, d3d10umddi/D3D10_DDI_USAGE_DYNAMIC, D3D10_DDI_RESOURCE_USAGE enumeration [Display Devices], UMDisplayDriver_Dx10param_Structs_1d4cddbd-58a0-45b3-b7a9-8b55654c37a7.xml, d3d10umddi/D3D10_DDI_RESOURCE_USAGE, d3d10umddi/D3D10_DDI_USAGE_IMMUTABLE, d3d10umddi/D3D10_DDI_USAGE_DEFAULT, display.d3d10_ddi_resource_usage, D3D10_DDI_USAGE_STAGING, D3D10_DDI_USAGE_DEFAULT, D3D10_DDI_USAGE_DYNAMIC, D3D10_DDI_USAGE_IMMUTABLE, d3d10umddi/D3D10_DDI_USAGE_STAGING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3d10umddi.h
apiname:
-	D3D10_DDI_RESOURCE_USAGE
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_RESOURCE_USAGE
---

# D3D10_DDI_RESOURCE_USAGE enumeration


## -description


The D3D10_DDI_RESOURCE_USAGE enumeration type contains values that identify how a resource is used.


## -syntax


````
typedef enum D3D10_DDI_RESOURCE_USAGE { 
  D3D10_DDI_USAGE_DEFAULT    = 0,
  D3D10_DDI_USAGE_IMMUTABLE  = 1,
  D3D10_DDI_USAGE_DYNAMIC    = 2,
  D3D10_DDI_USAGE_STAGING    = 3
} D3D10_DDI_RESOURCE_USAGE;
````


## -enum-fields




### -field D3D10_DDI_USAGE_DEFAULT

The resource is used at the highest level. An application cannot map to default resources. The resources can be bound to the graphics pipeline and used as copy destinations and sources. The Microsoft Direct3D runtime can call only the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md">ResourceUpdateSubresourceUP</a> function to update the contents directly with the CPU.


### -field D3D10_DDI_USAGE_IMMUTABLE

The resource is immutable and cannot be mapped or copied to. The resource can be bound to the pipeline and copied from. The Direct3D runtime cannot call <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md">ResourceUpdateSubresourceUP</a> to update the contents; therefore, the contents of the resource are provided at creation time.


### -field D3D10_DDI_USAGE_DYNAMIC

The resource is dynamic and should be resident in non-local video memory. The resource can also be mapped. However, when the resource is mapped, the CPU can only write (and not read) to the resource. Therefore, when mapped, the Direct3D runtime must use the D3D10_DDI_MAP_WRITE_DISCARD or D3D10_DDI_MAP_WRITE_NOOVERWRITE access level in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. Because this resource can be mapped, the runtime cannot call <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md">ResourceUpdateSubresourceUP</a>. 


### -field D3D10_DDI_USAGE_STAGING

The resource is a staging resource, which the user-mode display driver should allocate as system memory. The driver allocates system memory to ensure the proper alignment and pitch to enable DMA access to such a region of memory. Staging can be mapped by the application but cannot be bound to the 3-D graphics pipeline. However, staging resources are frequently used to copy between other non-mappable resources. Because this resource can be mapped, the runtime cannot call <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md">ResourceUpdateSubresourceUP</a>. 


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md">ResourceUpdateSubresourceUP</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_RESOURCE_USAGE enumeration%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

