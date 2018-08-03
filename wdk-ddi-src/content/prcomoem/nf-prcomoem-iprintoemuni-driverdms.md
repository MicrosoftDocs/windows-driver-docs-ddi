---
UID: NF:prcomoem.IPrintOemUni.DriverDMS
title: IPrintOemUni::DriverDMS
author: windows-driver-content
description: The IPrintOemUni::DriverDMS method allows a rendering plug-in for Unidrv to indicate that it uses a device-managed drawing surface.
old-location: print\iprintoemuni_driverdms.htm
tech.root: print
ms.assetid: b62e6752-0804-41c4-84f4-49ad145acaf3
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: DriverDMS, DriverDMS method [Print Devices], DriverDMS method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],DriverDMS method, IPrintOemUni.DriverDMS, IPrintOemUni::DriverDMS, prcomoem/IPrintOemUni::DriverDMS, print.iprintoemuni_driverdms, print_unidrv-pscript_rendering_fe76a6eb-0c5d-4e12-868b-c2e53df011e8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemUni.DriverDMS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::DriverDMS


## -description


The <code>IPrintOemUni::DriverDMS</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> to indicate that it uses a device-managed drawing surface.


## -parameters




### -param pDevObj

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a> structure.


### -param pBuffer

Caller-supplied pointer to a buffer to receive method-specified flags. (See the following Remarks section.)


### -param cbSize

Caller-supplied size, in bytes, of the buffer pointed to by <i>pBuffer</i>.


### -param pcbNeeded

Caller-supplied pointer to a location to receive the required minimum <i>pBuffer</i> size.


## -returns



The method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed

</td>
</tr>
</table>
 




## -remarks



A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::DriverDMS</code> method. The method will be called only if Unidrv finds a valid interface pointer to the OEM's rendering plug-in.

The <code>IPrintOemUni::DriverDMS</code> method allows a rendering plug-in to indicate that it will be using a device-managed drawing surface instead of the default GDI-managed surface.

The method must specify HOOK_-prefixed flags in the buffer pointed to by <i>pBuffer</i>, indicating which of the plug-in's graphics DDI hooking functions are to be called for the drawing surface. The HOOK_-prefixed flags are defined in winddi.h and described in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564183">EngAssociateSurface</a> function's description. Flags specified by <code>IPrintOemUni::DriverDMS</code> are passed by Unidrv to <b>EngAssociateSurface</b>. (Note that to support a device-managed surface, the rendering plug-in must hook out all drawing functions.) For more information, see <a href="https://msdn.microsoft.com/4403165f-c528-450e-9c96-77a9ce0778aa">Handling Device-Managed Surfaces</a>.

If <code>IPrintOemUni::DriverDMS</code> sets flags in the buffer pointed to by <i>pBuffer</i>, Unidrv creates a device-managed surface by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff564206">EngCreateDeviceSurface</a>. If <code>IPrintOemUni::DriverDMS</code> does not set any flags, Unidrv creates a GDI-managed surface by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff564199">EngCreateBitmap</a>. In either of these cases, <code>IPrintOemUni::DriverDMS</code> should return S_OK.

If the output buffer size specified by <i>cbSize</i> is too small, the method should specify the required size in the location pointed to by <i>pcbNeeded</i>, call <b>SetLastError</b>(ERROR_INSUFFICIENT_BUFFER), and return E_FAIL.



