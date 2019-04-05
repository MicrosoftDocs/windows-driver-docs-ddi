---
UID: NS:d3dkmthk._D3DKMT_ESCAPE
title: _D3DKMT_ESCAPE (d3dkmthk.h)
description: The D3DKMT_ESCAPE structure describes information that is exchanged with the display miniport driver.
old-location: display\d3dkmt_escape.htm
ms.assetid: db57ae5e-7060-4d45-99a5-e54c82b0aa05
ms.date: 05/10/2018
ms.keywords: D3DKMT_ESCAPE, D3DKMT_ESCAPE structure [Display Devices], OpenGL_Structs_b17fc4f1-d9cc-4ebe-a29a-66f9a93b9462.xml, _D3DKMT_ESCAPE, d3dkmthk/D3DKMT_ESCAPE, display.d3dkmt_escape
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_ESCAPE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_ESCAPE
---

# _D3DKMT_ESCAPE structure


## -description


The D3DKMT_ESCAPE structure describes information that is exchanged with the display miniport driver.


## -struct-fields




### -field hAdapter

[in] A handle to the graphics adapter that information is exchanged on.


### -field hDevice

[in] A handle to a display device that is optionally specified if the information to be exchanged is specific to a particular device.


### -field Type

[in] A value of type D3DKMT_ESCAPETYPE that indicates either to exchange information with the display miniport driver or to control kernel-mode components. The following table shows the possible values.

| **Value** | **Meaning** | 
|:--|:--|
| D3DKMT_ESCAPE_DRIVERPRIVATE (0) | The pPrivateDriverData member is targeted at the display miniport driver. The hardware vendor defines the format of the escape data. | 
| D3DKMT_ESCAPE_VIDMM (1) | **Do not use. For testing purposes only.** The OpenGL ICD controls the video memory manager (which is part of Dxgkrnl.sys). The buffer that pPrivateDriverData points to contains a [D3DKMT_VIDMM_ESCAPE](https://msdn.microsoft.com/library/windows/hardware/ff548410)  structure that supports various types of control of the video memory manager. | 
| D3DKMT_ESCAPE_TDRDBGCTRL (2) | **Do not use. For testing purposes only.** The escape operation lets the user control the behavior of the operating system's Timeout Detection and Recovery (TDR) process.<br/>This functionality is disabled by default. To enable this functionality, the TdrTestMode = TdrTestMode DWORD registry value, which is stored in the HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\GraphicsDrivers key, must be set to 1.<br/>The PrivateDriverDataSize member is set to sizeof(int). The pPrivateDriverData member is set to an integer with a value from the [D3DKMT_TDRDBGCTRLTYPE](https://msdn.microsoft.com/library/windows/hardware/ff548373)  enumeration type. |
| D3DKMT_ESCAPE_VIDSCH (3) | **Do not use. For testing purposes only.** The OpenGL ICD controls the graphics processing unit (GPU) scheduler (which is part of Dxgkrnl.sys). The buffer that pPrivateDriverData points to contains a [D3DKMT_VIDSCH_ESCAPE](https://msdn.microsoft.com/library/windows/hardware/ff548413) structure that supports preemption control and suspending or resuming the scheduler. |
| D3DKMT_ESCAPE_DEVICE (4) | **Do not use. For testing purposes only.** The OpenGL ICD controls the display device. The buffer that pPrivateDriverData points to contains a [D3DKMT_DEVICE_ESCAPE](https://msdn.microsoft.com/library/windows/hardware/ff547926) structure that supports obtaining the video present source from the primary allocation. | 
| D3DKMT_ESCAPE_DMM (5) | **Do not use. For testing purposes only.** The OpenGL ICD controls the display mode manager. The buffer that pPrivateDriverData points to contains a [D3DKMT_DMM_ESCAPE](https://msdn.microsoft.com/library/windows/hardware/ff547953)  structure. | 
| D3DKMT_ESCAPE_DEBUG_SNAPSHOT (6) | **Do not use. For testing purposes only.** The OpenGL ICD retrieves a debug snapshot buffer. The buffer that pPrivateDriverData points to contains a [D3DKMT_DEBUG_SNAPSHOT_ESCAPE](https://msdn.microsoft.com/library/windows/hardware/ff547865)  structure. | 
| D3DKMT_ESCAPE_SETDRIVERUPDATESTATUS (7) | **Do not use. For testing purposes only.** The OpenGL ICD sets the display miniport driver update status. |
| D3DKMT_ESCAPE_DRT_TEST (8) | **Do not use. For testing purposes only.** |
| D3DKMT_ESCAPE_DIAGNOSTICS (9) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_OUTPUTDUPL_SNAPSHOT (10) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_OUTPUTDUPL_DIAGNOSTICS (11) | **Do not use. For testing purposes only.** Supported starting with Windows 8. |
| D3DKMT_ESCAPE_BDD_PNP (12) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_BDD_FALLBACK (13) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_ACTIVATE_SPECIFIC_DIAG(14) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_MODES_PRUNED_OUT(15) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_WQHL_INFO(16) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_BRIGHTNESS(17) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_EDID_CACHE(18) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_GENERIC_ADAPTER_DIAG_INFO(19) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_MIRACAST_DISPLAY_REQUEST (20) | **Do not use. For testing purposes only.** Supported starting with Windows 8.1. | 
| D3DKMT_ESCAPE_HISTORY_BUFFER_STATUS (21) | **Do not use. For testing purposes only.** Supported starting with Windows 8.1. | 
| D3DKMT_ESCAPE_MIRACAST_ADAPTER_DIAG_INFO (23) | **Do not use. For testing purposes only.** Supported starting with Windows 8.1. | 
| D3DKMT_ESCAPE_WIN32K_START(1024) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_WIN32K_HIP_DEVICE_INFO(1024) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_WIN32K_QUERY_CD_ROTATION_BLOCK (1025) | **Do not use. For testing purposes only.** Supported starting with Windows 8. | 
| D3DKMT_ESCAPE_WIN32K_DPI_INFO (1026) | **Do not use. For testing purposes only.** Supported starting with Windows 8.1. | 
| D3DKMT_ESCAPE_WIN32K_PRESENTER_VIEW_INFO (1027) | **Do not use. For testing purposes only.** Supported starting with Windows 8.1. | 
| D3DKMT_ESCAPE_WIN32K_SYSTEM_DPI (1028) | **Do not use. For testing purposes only.** Supported starting with Windows 8.1. | 


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544541">D3DDDI_ESCAPEFLAGS</a> structure that indicates, in bit-field flags, how to share information. The OpenGL ICD should specify the <b>HardwareAccess</b> bit-field flag to indicate that the display miniport driver must access graphics hardware in such a way that the operating system must perform the <a href="https://msdn.microsoft.com/2b7c1eae-6527-469e-a2fa-74d2a1246bd3">second level of synchronization</a> into the display miniport driver for the <a href="https://msdn.microsoft.com/79a524cd-dec1-4ea8-a660-d9d9c644e162">DxgkDdiEscape</a> call. 


### -field pPrivateDriverData

[in/out] A pointer to a buffer that the OpenGL ICD allocates that contains information that the OpenGL ICD either exchanges with the display miniport driver or uses to control kernel-mode components. The following table describes the content of the buffer that <b>pPrivateDriverData</b> points to, depending on the value of <b>Type</b>.

| **Value of the Type member** | **Content of the pPrivateDriverData buffer** | 
|:--|:--|
| D3DKMT_ESCAPE_DRIVERPRIVATE | Driver-specific. The buffer is not usable unless a tight coupling exists between the OpenGL ICD and the display miniport driver. | 
| D3DKMT_ESCAPE_VIDMM | **Do not use. For testing purposes only.** A [D3DKMT_VIDMM_ESCAPE](https://msdn.microsoft.com/library/windows/hardware/ff548410) structure. | 
| D3DKMT_ESCAPE_TDRDBGCTRL | **Do not use. For testing purposes only.** A [D3DKMT_TDRDBGCTRLTYPE](https://msdn.microsoft.com/library/windows/hardware/ff548373) enumeration type. | 
| D3DKMT_ESCAPE_VIDSCH | **Do not use. For testing purposes only.** A [D3DKMT_VIDSCH_ESCAPE](https://msdn.microsoft.com/library/windows/hardware/ff548413) structure. | 
| D3DKMT_ESCAPE_DEVICE | **Do not use. For testing purposes only.** A [D3DKMT_DEVICE_ESCAPE](https://msdn.microsoft.com/library/windows/hardware/ff547926) structure. | 
| D3DKMT_ESCAPE_DMM | **Do not use. For testing purposes only.** A [D3DKMT_DMM_ESCAPE](https://msdn.microsoft.com/library/windows/hardware/ff547953)  structure. | 
| D3DKMT_ESCAPE_DEBUG_SNAPSHOT | **Do not use. For testing purposes only.** A [D3DKMT_DEBUG_SNAPSHOT_ESCAPE](https://msdn.microsoft.com/library/windows/hardware/ff547865) structure. |

### -field PrivateDriverDataSize

[in] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to. The OpenGL ICD must specify the size of the buffer when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a> function.

### -field hContext

[in] A handle to a context that is optionally specified if the information to be exchanged is specific to a particular device context. If the OpenGL ICD sets <b>hContext</b> to a non-NULL value, the ICD must have also set <b>hDevice</b> to a non-NULL value, and <b>hDevice</b> must correspond to the device that owns the context.

## -remarks



For testing purposes, the OpenGL ICD can pass a pointer to a D3DKMT_ESCAPE structure in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a> function to control the video memory manager and GPU scheduler (which are part of <i>Dxgkrnl.sys</i>) and the behavior of the operating system's TDR process. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547865">D3DKMT_DEBUG_SNAPSHOT_ESCAPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547926">D3DKMT_DEVICE_ESCAPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547953">D3DKMT_DMM_ESCAPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548373">D3DKMT_TDRDBGCTRLTYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548410">D3DKMT_VIDMM_ESCAPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548413">D3DKMT_VIDSCH_ESCAPE</a>
 

 

