---
UID: NC:dispmprt.DXGKCB_EVAL_ACPI_METHOD
title: DXGKCB_EVAL_ACPI_METHOD (dispmprt.h)
description: The DxgkCbEvalAcpiMethod function evaluates a specified ACPI method on a display adapter or on a child device of a display adapter.
old-location: display\dxgkcbevalacpimethod.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKCB_EVAL_ACPI_METHOD callback function"]
ms.keywords: DXGKCB_EVAL_ACPI_METHOD, DXGKCB_EVAL_ACPI_METHOD callback, DpFunctions_e18a1463-e8cb-4ecf-a50f-424dd71db4c3.xml, DxgkCbEvalAcpiMethod, DxgkCbEvalAcpiMethod callback function [Display Devices], display.dxgkcbevalacpimethod, dispmprt/DxgkCbEvalAcpiMethod
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKCB_EVAL_ACPI_METHOD
 - dispmprt/DXGKCB_EVAL_ACPI_METHOD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKCB_EVAL_ACPI_METHOD
---

# DXGKCB_EVAL_ACPI_METHOD callback function


## -description

The <b>DxgkCbEvalAcpiMethod</b> function evaluates a specified ACPI method on a display adapter or on a child device of a display adapter.

## -parameters

### -param DeviceHandle 

[in]
A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>.

### -param DeviceUid 

[in]
The unique identifier for the ACPI device on which the method will be evaluated. If the ACPI device is a child of the display adapter, this is the <b>ChildUid</b> member of the <a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structure that the display miniport driver filled in during <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>. If the ACPI device is the display adapter itself, this parameter must be set to DISPLAY_ADAPTER_HW_ID.

### -param AcpiInputBuffer 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_complex_v1">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a> structure (defined in <i>Acpiioct.h</i>) allocated and filled in by the display miniport driver. The structure contains the arguments that are required by the ACPI method. See the following Remarks section for more information.

### -param AcpiInputSize 

[in]
The total size, in bytes, of the buffer pointed to by <i>AcpiInputBuffer</i>.

### -param AcpiOutputBuffer 

[out]
A pointer to an ACPI_EVAL_OUTPUT_BUFFER structure (defined in <i>Acpiioct.h</i>) that receives the return value of the ACPI method. This parameter can be <b>NULL</b>.

### -param AcpiOutputSize 

[in]
The total size, in bytes, of the buffer pointed to by <i>AcpiOutputBuffer</i>.

## -returns

<b>DxgkCbEvalAcpiMethod</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## -remarks

To evaluate ACPI methods on an ACPI device, the device itself must be in the ACPI namespace. In addition, the display miniport driver must have set the lower 16 bits of the <b>ChildUid</b> value for any ACPI child devices that the display miniport driver reports to the identifier that ACPI reported.

Before it returns, <b>DxgkCbEvalAcpiMethod</b> resets the <b>Signature</b> member of the <a href="/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_complex_v1">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a> structure to ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE. In Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of the Windows operating systems, if the display miniport driver has child devices, it should set <b>Signature</b> to DXGK_ACPI_PASS_ARGS_TO_CHILDREN before it makes any call to <b>DxgkCbEvalAcpiMethod</b>.

<div class="alert"><b>Note</b>  The Microsoft DirectX graphics kernel subsystem cannot evaluate ACPI methods that are outside of the device's namespace. </div>
<div> </div>
<div class="alert"><b>Note</b>  Display miniport drivers can use <b>DxgkCbEvalAcpiMethod</b> only for lead-link graphics adapters. </div>
<div> </div>

#### Examples

The following code example shows how to evaluate an ACPI method.

```cpp
if (HwDeviceExtension->AcpiChildren != NULL) {
    ULONG ChildIndex;
    PACPI_METHOD_ARGUMENT AcpiChildrenArray = 
 &(((PACPI_EVAL_OUTPUT_BUFFER)HwDeviceExtension->AcpiChildren) 
   ->Argument[0]);
   ULONG ChildCount = ((PACPI_EVAL_OUTPUT_BUFFER) 
   (HwDeviceExtension->AcpiChildren))->Count;
  ULONG ChildUid;
  ACPI_EVAL_INPUT_BUFFER_COMPLEX AcpiInputBuffer = {'\0'};
   ACPI_EVAL_OUTPUT_BUFFER AcpiOutputBuffer;
    pDesiredStatus = ExAllocatePoolWithTag(PagedPool,
 sizeof(DESIRED_CHILD_STATUS) * ChildCount,
 ATI_TAG);

  if (pDesiredStatus == NULL) {
     Status = STATUS_NO_MEMORY;
        goto cleanup;
  }

 RtlZeroMemory(pDesiredStatus, sizeof(DESIRED_CHILD_STATUS) * ChildCount);

 for (ChildIndex = 0; ChildIndex < ChildCount; ChildIndex++) {
 // If not a video output child, go to the next child.
 if (AcpiChildrenArray[ChildIndex].Argument
   & ACPI_NON_VIDEO_OUTPUT_DEVICE) {
   continue;
      }
      // A video output child so the ChildUid is the VidPnTargetId.
       ChildUid = (AcpiChildrenArray[ChildIndex].Argument
   & ACPI_HARDWARE_ID) | HW_ID_DISPLAY_CHILD;

      // Query ACPI for the required state.
      //
  // Beginning with Windows Vista SP1 and Windows Server 2008,
  // use DXGK_ACPI_PASS_ARGS_TO_CHILDREN.

  #if (NTDDI_VERSION >= NTDDI_WIN6SP1)
   AcpiInputBuffer.Signature = 
   DXGK_ACPI_PASS_ARGS_TO_CHILDREN;
     #else
    AcpiInputBuffer.Signature = 
   ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE;
       #endif

     AcpiInputBuffer.MethodNameAsUlong = 
   ACPI_METHOD_OUTPUT_DGS;
     Status = DxgkCbEvalAcpiMethod(HwDeviceExtension->DeviceHandle,
         ChildUid,
         &AcpiInputBuffer,
         sizeof(ACPI_EVAL_INPUT_BUFFER_COMPLEX),
         &AcpiOutputBuffer,
         sizeof(ACPI_EVAL_OUTPUT_BUFFER));
     if (!NT_SUCCESS(Status)) {
         // Something really wrong
         goto cleanup;
     }
      // Determine what the new VidPn should be and
      // allow RecommendFunctionalVidPn to return it.
      // AcpiOutputBuffer.Argument[0].Argument == 1 indicates active
       // AcpiOutputBuffer.Argument[0].Argument == 0 
       // indicates not active
       pDesiredStatus[ChildIndex].bActive = 
   (AcpiOutputBuffer.Argument[0].Argument == 1) ? TRUE : FALSE;
      // Always use the first source because this is a keyboard shortcut.
      pDesiredStatus[ChildIndex].ulSourceId = 0;
      pDesiredStatus[ChildIndex].ulTargetId = ChildUid;
  }

 Status = InvalidateVidPnForHotKey(HwDeviceExtension, pDesiredStatus);
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_eval_input_buffer_complex_v1">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_notify_acpi_event">DxgkDdiNotifyAcpiEvent</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>

