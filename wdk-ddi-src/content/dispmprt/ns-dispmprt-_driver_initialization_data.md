---
UID: NS:dispmprt._DRIVER_INITIALIZATION_DATA
title: "_DRIVER_INITIALIZATION_DATA"
author: windows-driver-content
description: The DRIVER_INITIALIZATION_DATA structure contains pointers to functions implemented by the display miniport driver.
old-location: display\driver_initialization_data.htm
old-project: display
ms.assetid: 3ab00f9c-7ce9-41bf-85c5-96be31d19719
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDRIVER_INITIALIZATION_DATA, DRIVER_INITIALIZATION_DATA, DRIVER_INITIALIZATION_DATA structure [Display Devices], DmStructs_7b91bf58-dfda-4c7c-ae26-21e577bdc152.xml, PDRIVER_INITIALIZATION_DATA, PDRIVER_INITIALIZATION_DATA structure pointer [Display Devices], _DRIVER_INITIALIZATION_DATA, display.driver_initialization_data, dispmprt/DRIVER_INITIALIZATION_DATA, dispmprt/PDRIVER_INITIALIZATION_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dispmprt.h
api_name:
-	DRIVER_INITIALIZATION_DATA
product: Windows
targetos: Windows
req.typenames: DRIVER_INITIALIZATION_DATA, *PDRIVER_INITIALIZATION_DATA
---

# _DRIVER_INITIALIZATION_DATA structure


## -description


The <b>DRIVER_INITIALIZATION_DATA</b> structure contains pointers to functions implemented by the display miniport driver. The display miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function provides the Microsoft DirectX graphics kernel subsystem with entry points by filling in the members of this structure.


## -struct-fields




### -field Version

A positive integer that indicates the version of the functional interface implemented by the display miniport driver. The display miniport driver must set this member to <b>DXGKDDI_INTERFACE_VERSION</b>, which is defined in Dispmprt.h.


### -field DxgkDdiAddDevice

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -field DxgkDdiStartDevice

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function.


### -field DxgkDdiStopDevice

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/3c17c7cf-9cfa-421d-a503-88726519fb6c">DxgkDdiStopDevice</a> function.


### -field DxgkDdiRemoveDevice

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/0d5f96e8-dcb3-49e5-8347-ba20d757618b">DxgkDdiRemoveDevice</a> function.


### -field DxgkDdiDispatchIoRequest

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/e1973aca-cbc2-4780-a3b5-7601e1cc6c90">DxgkDdiDispatchIoRequest</a> function.


### -field DxgkDdiInterruptRoutine

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/eacfd42d-405c-4c23-8978-0f373a393e10">DxgkDdiInterruptRoutine</a> function.


### -field DxgkDdiDpcRoutine

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/2767906a-f084-4ccc-b24f-ba7d66c96477">DxgkDdiDpcRoutine</a> function.


### -field DxgkDdiQueryChildRelations

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a> function.


### -field DxgkDdiQueryChildStatus

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/478e0c52-4324-4062-8e1e-381808b0f481">DxgkDdiQueryChildStatus</a> function.


### -field DxgkDdiQueryDeviceDescriptor

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/0dfcc012-9fff-40b6-b71f-da2ca229896c">DxgkDdiQueryDeviceDescriptor</a> function.


### -field DxgkDdiSetPowerState

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/6462be4f-1f6e-4b85-a3ba-15820ee8605b">DxgkDdiSetPowerState</a> function.


### -field DxgkDdiNotifyAcpiEvent

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/fdefde51-0e90-4324-9c14-e8259fc872b3">DxgkDdiNotifyAcpiEvent</a> function.


### -field DxgkDdiResetDevice

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/e757e63d-6d78-4b20-9471-290f56c1bcde">DxgkDdiResetDevice</a> function.


### -field DxgkDdiUnload

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/336fa87a-6c3e-4337-90d9-b0ebeb355e68">DxgkDdiUnload</a> function.


### -field DxgkDdiQueryInterface

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/d8255f36-be3a-4b19-ac8d-8748ac9b6a24">DxgkDdiQueryInterface</a> function.


### -field DxgkDdiControlEtwLogging

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/c94a43bb-19d0-4894-80b0-885562fefea5">DxgkDdiControlEtwLogging</a> function.


### -field DxgkDdiQueryAdapterInfo

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function.


### -field DxgkDdiCreateDevice

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a> function.


### -field DxgkDdiCreateAllocation

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function. 


### -field DxgkDdiDestroyAllocation

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/cade544a-f9c6-4635-ab57-d09d694ca315">DxgkDdiDestroyAllocation</a> function.


### -field DxgkDdiDescribeAllocation

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/8ee65716-496c-4b0f-baa7-34a625847d5f">DxgkDdiDescribeAllocation</a> function. 


### -field DxgkDdiGetStandardAllocationDriverData

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/38a9859f-ed9f-41a5-9bf1-c734480499ea">DxgkDdiGetStandardAllocationDriverData</a> function. 


### -field DxgkDdiAcquireSwizzlingRange

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/f861e055-70db-4e0a-9c62-87e2d41f92ae">DxgkDdiAcquireSwizzlingRange</a> function.


### -field DxgkDdiReleaseSwizzlingRange

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/6c583a48-baa4-429f-b2fc-5f86859617cc">DxgkDdiReleaseSwizzlingRange</a> function.


### -field DxgkDdiPatch

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/363be784-0e3b-4f9a-a643-80857478bbae">DxgkDdiPatch</a> function.


### -field DxgkDdiSubmitCommand

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/de1925ab-e444-4cf6-acd9-8fdab26afcec">DxgkDdiSubmitCommand</a> function.


### -field DxgkDdiPreemptCommand

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/8cea02d4-f25e-4ff4-8c9e-aa360a764c4b">DxgkDdiPreemptCommand</a> function.


### -field DxgkDdiBuildPagingBuffer

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/d315ff53-4a9f-46a3-ad74-d65a5eb72de1">DxgkDdiBuildPagingBuffer</a> function.


### -field DxgkDdiSetPalette

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/3a46bf84-df62-4247-b842-d5b131c96428">DxgkDdiSetPalette</a> function that sets the palette for the display.


### -field DxgkDdiSetPointerPosition

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/b30e4f19-068c-4ab0-a2e9-b1f57592be1c">DxgkDdiSetPointerPosition</a> function.


### -field DxgkDdiSetPointerShape

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/36b462f7-5bad-4716-8138-af00d20e945b">DxgkDdiSetPointerShape</a> function.


### -field DxgkDdiResetFromTimeout

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/b9bfc801-33f6-4911-ab7d-8e3c99a5e2e9">DxgkDdiResetFromTimeout</a> function.


### -field DxgkDdiRestartFromTimeout

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/433babb7-9a53-4079-9a65-43a5ed0c201a">DxgkDdiRestartFromTimeout</a> function.


### -field DxgkDdiEscape

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/79a524cd-dec1-4ea8-a660-d9d9c644e162">DxgkDdiEscape</a> function.


### -field DxgkDdiCollectDbgInfo

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/f2f3d8f7-5a54-4830-b8f8-ac2f93096eda">DxgkDdiCollectDbgInfo</a> function.


### -field DxgkDdiQueryCurrentFence

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/0ca4d42f-3036-4b81-91a4-fbce7ac891fe">DxgkDdiQueryCurrentFence</a> function.


### -field DxgkDdiIsSupportedVidPn

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/96e96366-6306-4d20-8752-e942f2ed4069">DxgkDdiIsSupportedVidPn</a> function.


### -field DxgkDdiRecommendFunctionalVidPn

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/320a77a7-d7d4-47b9-8a40-2b6e12819e4b">DxgkDdiRecommendFunctionalVidPn</a> function.


### -field DxgkDdiEnumVidPnCofuncModality

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a> function.


### -field DxgkDdiSetVidPnSourceAddress

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a> function.


### -field DxgkDdiSetVidPnSourceVisibility

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/c94473b4-b898-456d-944d-8879adea16d1">DxgkDdiSetVidPnSourceVisibility</a> function.


### -field DxgkDdiCommitVidPn

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/979b86e9-f3ff-4022-8c00-b6afc2b1f747">DxgkDdiCommitVidPn</a>  function.


### -field DxgkDdiUpdateActiveVidPnPresentPath

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/3bf5ebf7-8113-4ab2-beb1-1a52df25ac37">DxgkDdiUpdateActiveVidPnPresentPath</a> function.


### -field DxgkDdiRecommendMonitorModes

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/1fa29ab6-1faa-4be6-ae87-4cac9057471d">DxgkDdiRecommendMonitorModes</a> function.


### -field DxgkDdiRecommendVidPnTopology

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/a7c31d2c-3893-4d25-837d-d4650aeb1cd1">DxgkDdiRecommendVidPnTopology</a> function.


### -field DxgkDdiGetScanLine

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/e37bb3c6-a0b6-409f-8a82-20ec7a931c6a">DxgkDdiGetScanLine</a> function.


### -field DxgkDdiStopCapture

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/e5d622cc-c550-44cf-8923-5092226066d9">DxgkDdiStopCapture</a> function.


### -field DxgkDdiControlInterrupt

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/d6bef242-bafc-4d9e-a729-d62ccdbd2667">DxgkDdiControlInterrupt</a> function.


### -field DxgkDdiCreateOverlay

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/1ccdd16d-fd76-4039-b538-86c77b4e8cbb">DxgkDdiCreateOverlay</a> function.

<div class="alert"><b>Note</b>  The following 5 functions are specific to the graphics context device that was created through <a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a>:</div>
<div> </div>

### -field DxgkDdiDestroyDevice

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/c067fe92-2364-4122-a7ed-03df7906ae64">DxgkDdiDestroyDevice</a> function.


### -field DxgkDdiOpenAllocation

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a> function.


### -field DxgkDdiCloseAllocation

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/f9c195d7-debe-495e-a355-e176d06884f8">DxgkDdiCloseAllocation</a> function. 


### -field DxgkDdiRender

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a> function.


### -field DxgkDdiPresent

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a> function.

<div class="alert"><b>Note</b>  The following 3 functions are specific to the overlay that was created through <a href="https://msdn.microsoft.com/1ccdd16d-fd76-4039-b538-86c77b4e8cbb">DxgkDdiCreateOverlay</a>:</div>
<div> </div>

### -field DxgkDdiUpdateOverlay

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/b131dbb9-1e11-4d04-97cb-e15ec2b025c7">DxgkDdiUpdateOverlay</a> function.


### -field DxgkDdiFlipOverlay

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/9e35a48b-1741-4ee2-8e15-6ce51ad4c0ad">DxgkDdiFlipOverlay</a> function.


### -field DxgkDdiDestroyOverlay

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/ea4672a2-ba21-42d4-9ff3-4fa611f86c90">DxgkDdiDestroyOverlay</a> function.

<div class="alert"><b>Note</b>  The following 2 functions are specific to supporting contexts:</div>
<div> </div>

### -field DxgkDdiCreateContext

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a> function.


### -field DxgkDdiDestroyContext

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/c21f62ab-c52e-43a2-a3a1-6fd6e5fbde01">DxgkDdiDestroyContext</a> function.


### -field DxgkDdiLinkDevice

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/fb9b7c58-1c4f-42e4-a59f-4a529d3caca2">DxgkDdiLinkDevice</a> function. Be aware that this function is specific to supporting linked graphics adapters.


### -field DxgkDdiSetDisplayPrivateDriverFormat

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/053fdf22-20c3-4b57-94f4-0613857abfa7">DxgkDdiSetDisplayPrivateDriverFormat</a> function.

<div class="alert"><b>Note</b>  The following 6 <a href="https://msdn.microsoft.com/F92F15A7-439D-4D45-84EE-A92D1E6AD779">reserved functions</a> declared in Dispmrt.h are available beginning with Windows 7:</div>
<div> </div>

### -field DxgkDdiDescribePageTable


      This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field DxgkDdiUpdatePageTable


      This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field DxgkDdiUpdatePageDirectory


      This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field DxgkDdiMovePageDirectory


      This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field DxgkDdiSubmitRender


      This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field DxgkDdiCreateAllocation2


      This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

<div class="alert"><b>Note</b>  The following 3 functions are available beginning with Windows 7:</div>
<div> </div>

### -field DxgkDdiRenderKm


      A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/5841934d-7e0a-4bb8-a7f8-17d8c0af351f">DxgkDdiRenderKm</a> function.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field Reserved


      This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field DxgkDdiQueryVidPnHWCapability


      A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/41af9528-4497-41aa-a65d-70352aa85f8c">DxgkDdiQueryVidPnHWCapability</a> function.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

<div class="alert"><b>Note</b>  The following 12 functions, including one reserved function, are available beginning with Windows 8:</div>
<div> </div>

### -field DxgkDdiSetPowerComponentFState

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/C68CC6F1-83D6-43D9-93F3-99E3A990C7D7">DxgkDdiSetPowerComponentFState</a> function.

Supported starting with Windows 8.


### -field DxgkDdiQueryDependentEngineGroup

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/42040ffc-40a3-4794-805c-7a165c47c8c9">DxgkDdiQueryDependentEngineGroup</a> function.

Supported starting with Windows 8.


### -field DxgkDdiQueryEngineStatus

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/87c99fcb-d25a-41b1-a1f3-9cf9ab7b141e">DxgkDdiQueryEngineStatus</a> function.

Supported starting with Windows 8.


### -field DxgkDdiResetEngine

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/9c2097b2-5742-422c-a650-7efff2484970">DxgkDdiResetEngine</a> function.

Supported starting with Windows 8.


### -field DxgkDdiStopDeviceAndReleasePostDisplayOwnership

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/6AF170BF-C422-4340-8935-31A4D4F3EFA5">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a> function.

Supported starting with Windows 8.


### -field DxgkDdiSystemDisplayEnable

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/D938F7F4-E1FA-4C63-A31D-5ED160276565">DxgkDdiSystemDisplayEnable</a> function.

Supported starting with Windows 8.


### -field DxgkDdiSystemDisplayWrite

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/5C0F9878-522C-4DDE-A790-54C94880F119">DxgkDdiSystemDisplayWrite</a> function.

Supported starting with Windows 8.


### -field DxgkDdiCancelCommand

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/c290c313-14ee-4554-9bb1-8adec1892426">DxgkDdiCancelCommand</a> function.

Supported starting with Windows 8.


### -field DxgkDdiGetChildContainerId

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/e7073fb3-0cb7-425e-9ffb-d7eaa963a70f">DxgkDdiGetChildContainerId</a> function.

Supported starting with Windows 8.


### -field DxgkDdiPowerRuntimeControlRequest

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/56535128-3107-4fb5-b0e1-2e913c386cc2">DxgkDdiPowerRuntimeControlRequest</a> function.

Supported starting with Windows 8.


### -field DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/95108e45-1a3a-4a75-8719-0caadb911469">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a> function.

Supported starting with Windows 8.1.


### -field DxgkDdiNotifySurpriseRemoval

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/4e6403e7-7463-479a-8be9-4136287b375e">DxgkDdiNotifySurpriseRemoval</a> function.

Supported starting with Windows 8.


### -field DxgkDdiGetNodeMetadata

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/ECE54E1C-5291-43AF-8A71-BD95DE5DF0A6">DxgkDdiGetNodeMetadata</a> function.

Supported starting with Windows 8.1.


### -field DxgkDdiSetPowerPState

This member is reserved and should be set to zero.

Supported starting with Windows 8.1.


### -field DxgkDdiControlInterrupt2

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/0C09CAB1-3DFC-4340-8FF2-99CAF7F13156">DxgkDdiControlInterrupt2</a> function.

Supported starting with Windows 10


### -field DxgkDdiCheckMultiPlaneOverlaySupport

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/8332DD64-B75E-40A4-9D98-3406187150F2">DxgkDdiCheckMultiPlaneOverlaySupport</a> function.

Supported starting with Windows 8.1.


### -field DxgkDdiCalibrateGpuClock

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/AF912508-D6EF-450D-AEC3-47D1C44D0DA0">DxgkDdiCalibrateGpuClock</a> function.

Supported starting with Windows 8.1.


### -field DxgkDdiFormatHistoryBuffer

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/84417629-5C12-4CB5-B147-0A558A4F9090">DxgkDdiFormatHistoryBuffer</a> function.

Supported starting with Windows 8.1.


### -field DxgkDdiRenderGdi

 


### -field DxgkDdiSubmitCommandVirtual

 


### -field DxgkDdiSetRootPageTable

 


### -field DxgkDdiGetRootPageTableSize

 


### -field DxgkDdiMapCpuHostAperture

 


### -field DxgkDdiUnmapCpuHostAperture

 


### -field DxgkDdiCheckMultiPlaneOverlaySupport2

 


### -field DxgkDdiCreateProcess

 


### -field DxgkDdiDestroyProcess

 


### -field DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2

 


### -field Reserved1

 


### -field Reserved2

 


### -field DxgkDdiPowerRuntimeSetDeviceHandle

 


### -field DxgkDdiSetStablePowerState

 


### -field DxgkDdiSetVideoProtectedRegion

 


### -field DxgkDdiCheckMultiPlaneOverlaySupport3

 


### -field DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay3

 


### -field DxgkDdiPostMultiPlaneOverlayPresent

 


### -field DxgkDdiValidateUpdateAllocationProperty

 


### -field DxgkDdiControlModeBehavior

 


### -field DxgkDdiUpdateMonitorLinkInfo

 


### -field DxgkDdiCreateHwContext

 


### -field DxgkDdiDestroyHwContext

 


### -field DxgkDdiCreateHwQueue

 


### -field DxgkDdiDestroyHwQueue

 


### -field DxgkDdiSubmitCommandToHwQueue

 


### -field DxgkDdiSwitchToHwContextList

 


### -field DxgkDdiResetHwEngine

 


### -field DxgkDdiCreatePeriodicFrameNotification

 


### -field DxgkDdiDestroyPeriodicFrameNotification

 


### -field DxgkDdiSetTimingsFromVidPn

 


### -field DxgkDdiSetTargetGamma

 


### -field DxgkDdiSetTargetContentType

 


### -field DxgkDdiSetTargetAnalogCopyProtection

 


### -field DxgkDdiSetTargetAdjustedColorimetry

 


### -field DxgkDdiDisplayDetectControl

 


### -field DxgkDdiQueryConnectionChange

 


### -field DxgkDdiExchangePreStartInfo

 


### -field DxgkDdiGetMultiPlaneOverlayCaps

 


### -field DxgkDdiGetPostCompositionCaps

 


### -field DxgkDdiUpdateHwContextState

 


### -field DxgkDdiCreateProtectedSession

 


### -field DxgkDdiDestroyProtectedSession

 




## -remarks



The following <b>typedef</b> declarations provide function data types from data types that are dereferenced pointers to functions:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef DXGKDDI_ADD_DEVICE  *PDXGKDDI_ADD_DEVICE;
typedef DXGKDDI_START_DEVICE  *PDXGKDDI_START_DEVICE;
typedef DXGKDDI_STOP_DEVICE  *PDXGKDDI_STOP_DEVICE;
typedef DXGKDDI_REMOVE_DEVICE  *PDXGKDDI_REMOVE_DEVICE;
typedef DXGKDDI_DISPATCH_IO_REQUEST  *PDXGKDDI_DISPATCH_IO_REQUEST;
typedef DXGKDDI_QUERY_CHILD_RELATIONS  *PDXGKDDI_QUERY_CHILD_RELATIONS;
typedef DXGKDDI_QUERY_CHILD_STATUS  *PDXGKDDI_QUERY_CHILD_STATUS;
typedef DXGKDDI_INTERRUPT_ROUTINE  *PDXGKDDI_INTERRUPT_ROUTINE;
typedef DXGKDDI_DPC_ROUTINE  *PDXGKDDI_DPC_ROUTINE;
typedef DXGKDDI_QUERY_DEVICE_DESCRIPTOR  *PDXGKDDI_QUERY_DEVICE_DESCRIPTOR;
typedef DXGKDDI_SET_POWER_STATE  *PDXGKDDI_SET_POWER_STATE;
typedef DXGKDDI_NOTIFY_ACPI_EVENT  *PDXGKDDI_NOTIFY_ACPI_EVENT;
typedef DXGKDDI_RESET_DEVICE  *PDXGKDDI_RESET_DEVICE;
typedef DXGKDDI_UNLOAD  *PDXGKDDI_UNLOAD;
typedef DXGKDDI_QUERY_INTERFACE  *PDXGKDDI_QUERY_INTERFACE;
typedef DXGKDDI_CONTROL_ETW_LOGGING  *PDXGKDDI_CONTROL_ETW_LOGGING;
typedef DXGKDDI_QUERYADAPTERINFO  *PDXGKDDI_QUERYADAPTERINFO;
typedef DXGKDDI_CREATEDEVICE  *PDXGKDDI_CREATEDEVICE;
typedef DXGKDDI_CREATEALLOCATION  *PDXGKDDI_CREATEALLOCATION;
typedef DXGKDDI_DESTROYALLOCATION  *PDXGKDDI_DESTROYALLOCATION;
typedef DXGKDDI_DESCRIBEALLOCATION  *PDXGKDDI_DESCRIBEALLOCATION;
typedef DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA  *PDXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA;
typedef DXGKDDI_ACQUIRESWIZZLINGRANGE  *PDXGKDDI_ACQUIRESWIZZLINGRANGE;
typedef DXGKDDI_RELEASESWIZZLINGRANGE  *PDXGKDDI_RELEASESWIZZLINGRANGE;
typedef DXGKDDI_PATCH  *PDXGKDDI_PATCH;
typedef DXGKDDI_SUBMITCOMMAND  *PDXGKDDI_SUBMITCOMMAND;
typedef DXGKDDI_PREEMPTCOMMAND  *PDXGKDDI_PREEMPTCOMMAND;
typedef DXGKDDI_BUILDPAGINGBUFFER  *PDXGKDDI_BUILDPAGINGBUFFER;
typedef DXGKDDI_SETPALETTE  *PDXGKDDI_SETPALETTE;
typedef DXGKDDI_SETPOINTERPOSITION  *PDXGKDDI_SETPOINTERPOSITION;
typedef DXGKDDI_SETPOINTERSHAPE  *PDXGKDDI_SETPOINTERSHAPE;
typedef DXGKDDI_RESETFROMTIMEOUT  *PDXGKDDI_RESETFROMTIMEOUT;
typedef DXGKDDI_RESTARTFROMTIMEOUT  *PDXGKDDI_RESTARTFROMTIMEOUT;
typedef DXGKDDI_ESCAPE  *PDXGKDDI_ESCAPE;
typedef DXGKDDI_COLLECTDBGINFO  *PDXGKDDI_COLLECTDBGINFO;
typedef DXGKDDI_QUERYCURRENTFENCE  *PDXGKDDI_QUERYCURRENTFENCE;
typedef DXGKDDI_ISSUPPORTEDVIDPN  *PDXGKDDI_ISSUPPORTEDVIDPN;
typedef DXGKDDI_RECOMMENDFUNCTIONALVIDPN  *PDXGKDDI_RECOMMENDFUNCTIONALVIDPN;
typedef DXGKDDI_ENUMVIDPNCOFUNCMODALITY  *PDXGKDDI_ENUMVIDPNCOFUNCMODALITY;
typedef DXGKDDI_SETVIDPNSOURCEADDRESS  *PDXGKDDI_SETVIDPNSOURCEADDRESS;
typedef DXGKDDI_SETVIDPNSOURCEVISIBILITY  *PDXGKDDI_SETVIDPNSOURCEVISIBILITY;
typedef DXGKDDI_COMMITVIDPN  *PDXGKDDI_COMMITVIDPN;
typedef DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH  *PDXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH;
typedef DXGKDDI_RECOMMENDMONITORMODES  *PDXGKDDI_RECOMMENDMONITORMODES;
typedef DXGKDDI_RECOMMENDVIDPNTOPOLOGY  *PDXGKDDI_RECOMMENDVIDPNTOPOLOGY;
typedef DXGKDDI_GETSCANLINE  *PDXGKDDI_GETSCANLINE;
typedef DXGKDDI_STOPCAPTURE  *PDXGKDDI_STOPCAPTURE;
typedef DXGKDDI_CONTROLINTERRUPT  *PDXGKDDI_CONTROLINTERRUPT;
typedef DXGKDDI_CREATEOVERLAY  *PDXGKDDI_CREATEOVERLAY;
typedef DXGKDDI_DESTROYDEVICE  *PDXGKDDI_DESTROYDEVICE;
typedef DXGKDDI_OPENALLOCATIONINFO  *PDXGKDDI_OPENALLOCATIONINFO;
typedef DXGKDDI_CLOSEALLOCATION  *PDXGKDDI_CLOSEALLOCATION;
typedef DXGKDDI_RENDER  *PDXGKDDI_RENDER;
typedef DXGKDDI_PRESENT  *PDXGKDDI_PRESENT;
typedef DXGKDDI_UPDATEOVERLAY  *PDXGKDDI_UPDATEOVERLAY;
typedef DXGKDDI_FLIPOVERLAY  *PDXGKDDI_FLIPOVERLAY;
typedef DXGKDDI_DESTROYOVERLAY  *PDXGKDDI_DESTROYOVERLAY;
typedef DXGKDDI_CREATECONTEXT  *PDXGKDDI_CREATECONTEXT; 
typedef DXGKDDI_DESTROYCONTEXT  *PDXGKDDI_DESTROYCONTEXT;
typedef DXGKDDI_LINK_DEVICE  *PDXGKDDI_LINK_DEVICE;
typedef DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT  *PDXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT;
#if (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WIN7)
typedef DXGKDDI_DESCRIBEPAGETABLE  *PDXGKDDI_DESCRIBEPAGETABLE;
typedef DXGKDDI_UPDATEPAGETABLE  *PDXGKDDI_UPDATEPAGETABLE;
typedef DXGKDDI_UPDATEPAGEDIRECTORY  *PDXGKDDI_UPDATEPAGEDIRECTORY;
typedef DXGKDDI_MOVEPAGEDIRECTORY  *PDXGKDDI_MOVEPAGEDIRECTORY;
typedef DXGKDDI_SUBMITRENDER  *PDXGKDDI_SUBMITRENDER;
typedef DXGKDDI_CREATEALLOCATION2  *PDXGKDDI_CREATEALLOCATION2;
typedef DXGKDDI_RENDERKM  *PDXGKDDI_RENDERKM;
typedef DXGKDDI_QUERYVIDPNHWCAPABILITY  *PDXGKDDI_QUERYVIDPNHWCAPABILITY;
#endif // DXGKDDI_INTERFACE_VERSION_WIN7
#if (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WIN8)
typedef DXGKDDISETPOWERCOMPONENTFSTATE  *PDXGKDDISETPOWERCOMPONENTFSTATE;
typedef DXGKDDI_QUERYDEPENDENTENGINEGROUP  *PDXGKDDI_QUERYDEPENDENTENGINEGROUP;
typedef DXGKDDI_QUERYENGINESTATUS  *PDXGKDDI_QUERYENGINESTATUS;
typedef DXGKDDI_RESETENGINE  *PDXGKDDI_RESETENGINE;
typedef DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP  *PDXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP;
typedef DXGKDDI_SYSTEM_DISPLAY_ENABLE  *PDXGKDDI_SYSTEM_DISPLAY_ENABLE;
typedef DXGKDDI_SYSTEM_DISPLAY_WRITE  *PDXGKDDI_SYSTEM_DISPLAY_WRITE; 
typedef DXGKDDI_CANCELCOMMAND  *PDXGKDDI_CANCELCOMMAND;
typedef DXGKDDI_GET_CHILD_CONTAINER_ID  *PDXGKDDI_GET_CHILD_CONTAINER_ID;
typedef DXGKDDIPOWERRUNTIMECONTROLREQUEST  *PDXGKDDIPOWERRUNTIMECONTROLREQUEST; 
typedef DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY *PDXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY;
typedef DXGKDDI_NOTIFY_SURPRISE_REMOVAL         *PDXGKDDI_NOTIFY_SURPRISE_REMOVAL;
#endif //
#if (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
typedef DXGKDDI_GETNODEMETADATA  *PDXGKDDI_GETNODEMETADATA;
typedef DXGKDDI_CONTROLINTERRUPT2  *PDXGKDDI_CONTROLINTERRUPT2;
typedef DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT  *PDXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT;
typedef DXGKDDI_FORMATHISTORYBUFFER  *PDXGKDDI_FORMATHISTORYBUFFER;
typedef DXGKDDI_CALIBRATEGPUCLOCK  *PDXGKDDI_CALIBRATEGPUCLOCK; 
#endif</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556157">DriverEntry of Display Miniport Driver</a>
 

 

