---
UID: NF:dispmprt.DxgkInitialize
title: DxgkInitialize function
author: windows-driver-content
description: The DxgkInitialize function loads and initializes the DirectX graphics kernel subsystem (Dxgkrnl.sys).
old-location: display\dxgkinitialize.htm
old-project: display
ms.assetid: 0eda4184-2852-4a31-b4da-1fbb99ed4670
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgkinitialize, dispmprt/DxgkInitialize, DxgkInitialize function [Display Devices], DxgkInitialize, DpFunctions_a3ffc7d5-f2bc-42f0-97f3-411bfe7b95e7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dispmprt.h
apiname:
-	DxgkInitialize
product: Windows
targetos: Windows
req.typenames: DXGK_SURPRISE_REMOVAL_TYPE
---

# DxgkInitialize function


## -description


The <b>DxgkInitialize</b> function loads and initializes the DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>).


## -syntax


````
NTSTATUS DxgkInitialize(
  _In_ PDRIVER_OBJECT              DriverObject,
  _In_ PUNICODE_STRING             RegistryPath,
  _In_ PDRIVER_INITIALIZATION_DATA DriverInitializationData
);
````


## -parameters




### -param DriverObject [in]

A pointer to a <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure. The display miniport driver previously obtained this pointer in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function.


### -param RegistryPath [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that supplies the path to the driver's service registry key.  The display miniport driver previously obtained this pointer in its <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> function.


### -param DriverInitializationData [in]

A pointer to a <a href="..\dispmprt\ns-dispmprt-_driver_initialization_data.md">DRIVER_INITIALIZATION_DATA</a> structure that supplies the DirectX graphics kernel subsystem with pointers to functions implemented by the display miniport driver.


## -returns



<b>DxgkInitialize</b>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



The display miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function calls <b>DxgkInitialize</b>.


#### Examples

The following code example shows an implementation of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> in which <b>DxgkInitialize</b> is called.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
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
                          &amp;DriverInitializationData);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>



<a href="..\dispmprt\ns-dispmprt-_driver_initialization_data.md">DRIVER_INITIALIZATION_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556157">DriverEntry of Display Miniport Driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DxgkInitialize function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

