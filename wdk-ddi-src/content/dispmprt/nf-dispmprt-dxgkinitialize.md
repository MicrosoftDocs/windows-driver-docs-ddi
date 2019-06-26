---
UID: NF:dispmprt.DxgkInitialize
title: DxgkInitialize function (dispmprt.h)
description: The DxgkInitialize function loads and initializes the DirectX graphics kernel subsystem (Dxgkrnl.sys).
old-location: display\dxgkinitialize.htm
tech.root: display
ms.assetid: 0eda4184-2852-4a31-b4da-1fbb99ed4670
ms.date: 05/10/2018
ms.keywords: DpFunctions_a3ffc7d5-f2bc-42f0-97f3-411bfe7b95e7.xml, DxgkInitialize, DxgkInitialize function [Display Devices], display.dxgkinitialize, dispmprt/DxgkInitialize
ms.topic: function
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Displib.lib
api_name:
- DxgkInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# DxgkInitialize function


## -description


The <b>DxgkInitialize</b> function loads and initializes the DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>).


## -parameters




### -param DriverObject [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a> structure. The display miniport driver previously obtained this pointer in its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function.


### -param RegistryPath [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that supplies the path to the driver's service registry key.  The display miniport driver previously obtained this pointer in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a> function.


### -param DriverInitializationData [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_driver_initialization_data">DRIVER_INITIALIZATION_DATA</a> structure that supplies the DirectX graphics kernel subsystem with pointers to functions implemented by the display miniport driver.


## -returns



<b>DxgkInitialize</b>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function calls <b>DxgkInitialize</b>.


#### Examples

The following code example shows an implementation of <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> in which <b>DxgkInitialize</b> is called.

```cpp
NTSTATUS
DriverEntry(
    IN PDRIVER_OBJECT DriverObject,
    IN PUNICODE_STRING RegistryPath
    )
{
    DRIVER_INITIALIZATION_DATA DriverInitializationData = {'\0'};

    PAGED_CODE();

    if (! ARGUMENT_PRESENT(DriverObject) ||
        ! ARGUMENT_PRESENT(RegistryPath))
    {
        return STATUS_INVALID_PARAMETER;
    }

    // Fill in the DriverInitializationData structure and call DxgkInitialize()
    DriverInitializationData.Version  = DXGKDDI_INTERFACE_VERSION;
 
    DriverInitializationData.DxgkDdiAddDevice  = AtiAddDevice;
    DriverInitializationData.DxgkDdiStartDevice  = AtiStartDevice;
    DriverInitializationData.DxgkDdiStopDevice  = AtiStopDevice;
    DriverInitializationData.DxgkDdiRemoveDevice  = AtiRemoveDevice;
    DriverInitializationData.DxgkDdiDispatchIoRequest  = AtiDispatchIoRequest;
    DriverInitializationData.DxgkDdiInterruptRoutine  = AtiInterruptRoutine;
    DriverInitializationData.DxgkDdiDpcRoutine  = AtiDpcRoutine;
    DriverInitializationData.DxgkDdiQueryChildRelations  = AtiQueryChildRelations;
    DriverInitializationData.DxgkDdiQueryChildStatus   = AtiQueryChildStatus;
    DriverInitializationData.DxgkDdiQueryDeviceDescriptor  = AtiQueryDeviceDescriptor;
    DriverInitializationData.DxgkDdiSetPowerState  = AtiSetPowerState;
    DriverInitializationData.DxgkDdiNotifyAcpiEvent  = AtiNotifyAcpiEvent;
    DriverInitializationData.DxgkDdiResetDevice  = AtiResetDevice;
    DriverInitializationData.DxgkDdiUnload  = AtiUnload;
    DriverInitializationData.DxgkDdiQueryInterface  = AtiQueryInterface;
    DriverInitializationData.DxgkDdiControlEtwLogging  = D3DDDIControlEtwLogging;

    DriverInitializationData.DxgkDdiQueryAdapterInfo  = D3DDDIQueryAdapterInfo;
    DriverInitializationData.DxgkDdiCreateDevice  = D3DDDICreateDevice;
    DriverInitializationData.DxgkDdiCreateAllocation  = D3DDDICreateAllocation;
    DriverInitializationData.DxgkDdiDestroyAllocation  = D3DDDIDestroyAllocation;

    DriverInitializationData.DxgkDdiCreateOverlay  = D3DDDICreateOverlay;
    DriverInitializationData.DxgkDdiUpdateOverlay  = D3DDDIUpdateOverlay;
    DriverInitializationData.DxgkDdiFlipOverlay  = D3DDDIFlipOverlay;
    DriverInitializationData.DxgkDdiDestroyOverlay  = D3DDDIDestroyOverlay;

    DriverInitializationData.DxgkDdiDescribeAllocation  = D3DDDIDescribeAllocation;
    DriverInitializationData.DxgkDdiGetStandardAllocationDriverData = D3DDDIGetStandardAllocationDriverData;

    DriverInitializationData.DxgkDdiAcquireSwizzlingRange  = D3DDDIAcquireSwizzlingRange;
    DriverInitializationData.DxgkDdiReleaseSwizzlingRange  = D3DDDIReleaseSwizzlingRange;

    DriverInitializationData.DxgkDdiOpenAllocation  = D3DDDIOpenAllocation;
    DriverInitializationData.DxgkDdiCloseAllocation  = D3DDDICloseAllocation;

    DriverInitializationData.DxgkDdiPatch  = D3DDDIPatchDmaBuffer;
    DriverInitializationData.DxgkDdiSubmitCommand  = D3DDDISubmitCommand;
    DriverInitializationData.DxgkDdiBuildPagingBuffer  = D3DDDIBuildPagingBuffer;
    DriverInitializationData.DxgkDdiSetPalette  = D3DDDISetPalette;
    DriverInitializationData.DxgkDdiSetPointerShape  = D3DDDISetPointerShape;
    DriverInitializationData.DxgkDdiSetPointerPosition  = D3DDDISetPointerPosition;
    DriverInitializationData.DxgkDdiPreemptCommand  = D3DDDIPreemptCommand;

    DriverInitializationData.DxgkDdiDestroyDevice  = D3DDDIDestroyDevice;
    DriverInitializationData.DxgkDdiRender  = D3DDDIRender;
    DriverInitializationData.DxgkDdiRenderKm  = D3DDDIRenderKm;    DriverInitializationData.DxgkDdiPresent  = D3DDDIPresent;
    DriverInitializationData.DxgkDdiResetFromTimeout  = D3DDDIResetFromTimeout;
    DriverInitializationData.DxgkDdiRestartFromTimeout  = D3DDDIRestartFromTimeout;
    DriverInitializationData.DxgkDdiEscape  = D3DDDIEscape;
    DriverInitializationData.DxgkDdiCollectDbgInfo  = D3DDDICollectDbgInfo;
    DriverInitializationData.DxgkDdiQueryCurrentFence  = D3DDDIQueryCurrentFence;
    DriverInitializationData.DxgkDdiControlInterrupt  = D3DDDIControlInterrupt;
    DriverInitializationData.DxgkDdiGetScanLine  = D3DDDIGetScanLine;
    DriverInitializationData.DxgkDdiStopCapture  = D3DDDI DxgkDdiStopCapture;    DriverInitializationData.DxgkDdiSetVidPnSourceAddress  = D3DDDISetVidPnSourceAddress;
    DriverInitializationData.DxgkDdiSetVidPnSourceVisibility  = D3DDDISetVidPnSourceVisibility;
    DriverInitializationData.DxgkDdiUpdateActiveVidPnPresentPath  = D3DDDIUpdateActiveVidPnPresentPath;
    DriverInitializationData.DxgkDdiCommitVidPn  = D3DDDICommitVidPn;
    DriverInitializationData.DxgkDdiRecommendMonitorModes  = D3DDDIRecommendMonitorModes;
    DriverInitializationData.DxgkDdiRecommendVidPnTopology  = D3DDDIRecommendVidPnTopology;

    DriverInitializationData.DxgkDdiCreateContext  = D3DDDICreateContext;
    DriverInitializationData.DxgkDdiDestroyContext  = D3DDDIDestroyContext;

    DriverInitializationData.DxgkDdiLinkDevice  = D3DDDILinkDevice;
    DriverInitializationData.DxgkDdiSetDisplayPrivateDriverFormat  = D3DDDISetDisplayPrivateDriverFormat;
    DriverInitializationData.DxgkDdiRecommendFunctionalVidPn  = D3DDDIRecommendFunctionalVidPn_XddmParity;
    DriverInitializationData.DxgkDdiEnumVidPnCofuncModality  = D3DDDIEnumVidPnCofuncModality_XddmParity;
    DriverInitializationData.DxgkDdiIsSupportedVidPn  = D3DDDIIsSupportedVidPn_XddmParity;
    DriverInitializationData.DxgkDdiQueryVidPnHWCapability  = D3DDDI DxgkDdiQueryVidPnHWCapability;

    return DxgkInitialize(DriverObject,
                          RegistryPath,
                          &DriverInitializationData);
}
```


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_driver_initialization_data">DRIVER_INITIALIZATION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/display/driverentry-of-display-miniport-driver">DriverEntry of Display Miniport Driver</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

