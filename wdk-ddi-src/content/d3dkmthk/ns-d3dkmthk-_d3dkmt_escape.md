---
UID: NS:d3dkmthk._D3DKMT_ESCAPE
title: "_D3DKMT_ESCAPE"
author: windows-driver-content
description: The D3DKMT_ESCAPE structure describes information that is exchanged with the display miniport driver.
old-location: display\d3dkmt_escape.htm
old-project: display
ms.assetid: db57ae5e-7060-4d45-99a5-e54c82b0aa05
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_ESCAPE, D3DKMT_ESCAPE structure [Display Devices], D3DKMT_ESCAPETYPE, OpenGL_Structs_b17fc4f1-d9cc-4ebe-a29a-66f9a93b9462.xml, _D3DKMT_ESCAPE, d3dkmthk/D3DKMT_ESCAPE, display.d3dkmt_escape
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_ESCAPE
product: Windows
targetos: Windows
req.typenames: D3DKMT_ESCAPE
---

# _D3DKMT_ESCAPE structure


## -description


The D3DKMT_ESCAPE structure describes information that is exchanged with the display miniport driver.


## -syntax


````
typedef struct _D3DKMT_ESCAPE {
  D3DKMT_HANDLE      hAdapter;
  D3DKMT_HANDLE      hDevice;
  D3DKMT_ESCAPETYPE  Type;
  D3DDDI_ESCAPEFLAGS Flags;
  VOID               *pPrivateDriverData;
  UINT               PrivateDriverDataSize;
  D3DKMT_HANDLE      hContext;
} D3DKMT_ESCAPE;
````


## -struct-fields




### -field hAdapter

[in] A handle to the graphics adapter that information is exchanged on.


### -field hDevice

[in] A handle to a display device that is optionally specified if the information to be exchanged is specific to a particular device.


### -field Type

[in] A value of type D3DKMT_ESCAPETYPE that indicates either to exchange information with the display miniport driver or to control kernel-mode components. The following table shows the possible values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_DRIVERPRIVATE (0)

</td>
<td>
The <b>pPrivateDriverData</b> member is targeted at the display miniport driver. The hardware vendor defines the format of the escape data.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_VIDMM (1)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

The OpenGL ICD controls the video memory manager (which is part of <i>Dxgkrnl.sys</i>). The buffer that <b>pPrivateDriverData</b> points to contains a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_vidmm_escape.md">D3DKMT_VIDMM_ESCAPE</a> structure that supports various types of control of the video memory manager.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_TDRDBGCTRL (2)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

The escape operation lets the user control the behavior of the operating system's Timeout Detection and Recovery (TDR) process. 

This functionality is disabled by default. To enable this functionality, the TdrTestMode<b></b> = TdrTestMode DWORD registry value, which is stored in the HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\GraphicsDrivers key, must be set to 1.

The <b>PrivateDriverDataSize</b> member is set to <b>sizeof</b>(int). The <b>pPrivateDriverData</b> member is set to an integer with a value from the <a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_tdrdbgctrltype.md">D3DKMT_TDRDBGCTRLTYPE</a> enumeration type.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_VIDSCH (3)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

The OpenGL ICD controls the graphics processing unit (GPU) scheduler (which is part of <i>Dxgkrnl.sys</i>). The buffer that <b>pPrivateDriverData</b> points to contains a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_vidsch_escape.md">D3DKMT_VIDSCH_ESCAPE</a> structure that supports preemption control and suspending or resuming the scheduler.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_DEVICE (4)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

The OpenGL ICD controls the display device. The buffer that <b>pPrivateDriverData</b> points to contains a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_device_escape.md">D3DKMT_DEVICE_ESCAPE</a> structure that supports obtaining the video present source from the primary allocation.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_DMM (5)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

The OpenGL ICD controls the display mode manager. The buffer that <b>pPrivateDriverData</b> points to contains a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_dmm_escape.md">D3DKMT_DMM_ESCAPE</a> structure.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_DEBUG_SNAPSHOT (6)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

The OpenGL ICD retrieves a debug snapshot buffer. The buffer that <b>pPrivateDriverData</b> points to contains a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_debug_snapshot_escape.md">D3DKMT_DEBUG_SNAPSHOT_ESCAPE</a> structure.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_SETDRIVERUPDATESTATUS (7)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

The OpenGL ICD sets the display miniport driver update status. 

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_DRT_TEST (8)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_DIAGNOSTICS (9)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_OUTPUTDUPL_SNAPSHOT (10)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_OUTPUTDUPL_DIAGNOSTICS  (11)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_BDD_PNP (12)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_BDD_FALLBACK (13)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_ACTIVATE_SPECIFIC_DIAG(14)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_MODES_PRUNED_OUT(15)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_WQHL_INFO(16)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
        D3DKMT_ESCAPE_BRIGHTNESS(17)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
    D3DKMT_ESCAPE_EDID_CACHE(18)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_GENERIC_ADAPTER_DIAG_INFO(19)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_MIRACAST_DISPLAY_REQUEST (20)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.1.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_HISTORY_BUFFER_STATUS (21)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.1.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_MIRACAST_ADAPTER_DIAG_INFO (23)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.1.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_WIN32K_START(1024)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_WIN32K_HIP_DEVICE_INFO(1024)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_WIN32K_QUERY_CD_ROTATION_BLOCK (1025)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_WIN32K_DPI_INFO (1026)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.1.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_WIN32K_PRESENTER_VIEW_INFO (1027)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.1.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_WIN32K_SYSTEM_DPI (1028)

</td>
<td>
<b>Do not use. For testing purposes only.</b>

Supported starting with Windows 8.1.

</td>
</tr>
</table>
 


### -field Flags

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_escapeflags.md">D3DDDI_ESCAPEFLAGS</a> structure that indicates, in bit-field flags, how to share information. The OpenGL ICD should specify the <b>HardwareAccess</b> bit-field flag to indicate that the display miniport driver must access graphics hardware in such a way that the operating system must perform the <a href="https://msdn.microsoft.com/2b7c1eae-6527-469e-a2fa-74d2a1246bd3">second level of synchronization</a> into the display miniport driver for the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_escape.md">DxgkDdiEscape</a> call. 


### -field pPrivateDriverData

[in/out] A pointer to a buffer that the OpenGL ICD allocates that contains information that the OpenGL ICD either exchanges with the display miniport driver or uses to control kernel-mode components. The following table describes the content of the buffer that <b>pPrivateDriverData</b> points to, depending on the value of <b>Type</b>.

<table>
<tr>
<th>Value of the Type member</th>
<th>Content of the pPrivateDriverData buffer</th>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_DRIVERPRIVATE

</td>
<td>
Driver-specific. The buffer is not usable unless a tight coupling exists between the OpenGL ICD and the display miniport driver.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_VIDMM

</td>
<td>
<b>Do not use. For testing purposes only.</b>

A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_vidmm_escape.md">D3DKMT_VIDMM_ESCAPE</a> structure.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_TDRDBGCTRL

</td>
<td>
<b>Do not use. For testing purposes only.</b>

A <a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_tdrdbgctrltype.md">D3DKMT_TDRDBGCTRLTYPE</a> enumeration type.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_VIDSCH

</td>
<td>
<b>Do not use. For testing purposes only.</b>

A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_vidsch_escape.md">D3DKMT_VIDSCH_ESCAPE</a> structure.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_DEVICE

</td>
<td>
<b>Do not use. For testing purposes only.</b>

A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_device_escape.md">D3DKMT_DEVICE_ESCAPE</a> structure.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_DMM

</td>
<td>
<b>Do not use. For testing purposes only.</b>

A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_dmm_escape.md">D3DKMT_DMM_ESCAPE</a> structure.

</td>
</tr>
<tr>
<td>
D3DKMT_ESCAPE_DEBUG_SNAPSHOT

</td>
<td>
<b>Do not use. For testing purposes only.</b>

A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_debug_snapshot_escape.md">D3DKMT_DEBUG_SNAPSHOT_ESCAPE</a> structure.

</td>
</tr>
</table>
 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to. The OpenGL ICD must specify the size of the buffer when it calls the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a> function.


### -field hContext

[in] A handle to a context that is optionally specified if the information to be exchanged is specific to a particular device context. If the OpenGL ICD sets <b>hContext</b> to a non-NULL value, the ICD must have also set <b>hDevice</b> to a non-NULL value, and <b>hDevice</b> must correspond to the device that owns the context.


## -remarks



For testing purposes, the OpenGL ICD can pass a pointer to a D3DKMT_ESCAPE structure in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a> function to control the video memory manager and GPU scheduler (which are part of <i>Dxgkrnl.sys</i>) and the behavior of the operating system's TDR process. 




## -see-also

<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_tdrdbgctrltype.md">D3DKMT_TDRDBGCTRLTYPE</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_device_escape.md">D3DKMT_DEVICE_ESCAPE</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_dmm_escape.md">D3DKMT_DMM_ESCAPE</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_vidsch_escape.md">D3DKMT_VIDSCH_ESCAPE</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_vidmm_escape.md">D3DKMT_VIDMM_ESCAPE</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_debug_snapshot_escape.md">D3DKMT_DEBUG_SNAPSHOT_ESCAPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_ESCAPE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

