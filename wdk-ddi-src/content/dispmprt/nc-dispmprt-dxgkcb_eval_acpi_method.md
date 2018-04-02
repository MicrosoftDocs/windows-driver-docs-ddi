---
UID: NC:dispmprt.DXGKCB_EVAL_ACPI_METHOD
title: DXGKCB_EVAL_ACPI_METHOD
author: windows-driver-content
description: The DxgkCbEvalAcpiMethod function evaluates a specified ACPI method on a display adapter or on a child device of a display adapter.
old-location: display\dxgkcbevalacpimethod.htm
old-project: display
ms.assetid: ce54cf4e-5b50-4142-b3c7-ff29b7bdbb35
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKCB_EVAL_ACPI_METHOD, DpFunctions_e18a1463-e8cb-4ecf-a50f-424dd71db4c3.xml, DxgkCbEvalAcpiMethod, DxgkCbEvalAcpiMethod callback function [Display Devices], display.dxgkcbevalacpimethod, dispmprt/DxgkCbEvalAcpiMethod
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkCbEvalAcpiMethod
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKCB_EVAL_ACPI_METHOD callback


## -description


The <b>DxgkCbEvalAcpiMethod</b> function evaluates a specified ACPI method on a display adapter or on a child device of a display adapter.


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>.


### -param DeviceUid [in]

The unique identifier for the ACPI device on which the method will be evaluated. If the ACPI device is a child of the display adapter, this is the <b>ChildUid</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a> structure that the display miniport driver filled in during <a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>. If the ACPI device is the display adapter itself, this parameter must be set to DISPLAY_ADAPTER_HW_ID.


### -param AcpiInputBuffer [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536116">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a> structure (defined in <i>Acpiioct.h</i>) allocated and filled in by the display miniport driver. The structure contains the arguments that are required by the ACPI method. See the following Remarks section for more information.


### -param AcpiInputSize [in]

The total size, in bytes, of the buffer pointed to by <i>AcpiInputBuffer</i>.


### -param AcpiOutputBuffer [out]

A pointer to an ACPI_EVAL_OUTPUT_BUFFER structure (defined in <i>Acpiioct.h</i>) that receives the return value of the ACPI method. This parameter can be <b>NULL</b>.


### -param AcpiOutputSize [in]

The total size, in bytes, of the buffer pointed to by <i>AcpiOutputBuffer</i>.


## -returns



<b>DxgkCbEvalAcpiMethod</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



To evaluate ACPI methods on an ACPI device, the device itself must be in the ACPI namespace. In addition, the display miniport driver must have set the lower 16 bits of the <b>ChildUid</b> value for any ACPI child devices that the display miniport driver reports to the identifier that ACPI reported.

Before it returns, <b>DxgkCbEvalAcpiMethod</b> resets the <b>Signature</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536116">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a> structure to ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE. In Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of the Windows operating systems, if the display miniport driver has child devices, it should set <b>Signature</b> to DXGK_ACPI_PASS_ARGS_TO_CHILDREN before it makes any call to <b>DxgkCbEvalAcpiMethod</b>.

<div class="alert"><b>Note</b>  The Microsoft DirectX graphics kernel subsystem cannot evaluate ACPI methods that are outside of the device's namespace. </div>
<div> </div>
<div class="alert"><b>Note</b>  Display miniport drivers can use <b>DxgkCbEvalAcpiMethod</b> only for lead-link graphics adapters. </div>
<div> </div>

#### Examples

The following code example shows how to evaluate an ACPI method.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>if (HwDeviceExtension-&gt;AcpiChildren != NULL) {
    ULONG ChildIndex;
    PACPI_METHOD_ARGUMENT AcpiChildrenArray = 
 &amp;(((PACPI_EVAL_OUTPUT_BUFFER)HwDeviceExtension-&gt;AcpiChildren) 
   -&gt;Argument[0]);
   ULONG ChildCount = ((PACPI_EVAL_OUTPUT_BUFFER) 
   (HwDeviceExtension-&gt;AcpiChildren))-&gt;Count;
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

 for (ChildIndex = 0; ChildIndex &lt; ChildCount; ChildIndex++) {
 // If not a video output child, go to the next child.
 if (AcpiChildrenArray[ChildIndex].Argument
   &amp; ACPI_NON_VIDEO_OUTPUT_DEVICE) {
   continue;
      }
      // A video output child so the ChildUid is the VidPnTargetId.
       ChildUid = (AcpiChildrenArray[ChildIndex].Argument
   &amp; ACPI_HARDWARE_ID) | HW_ID_DISPLAY_CHILD;

      // Query ACPI for the required state.
      //
  // Beginning with Windows Vista SP1 and Windows Server 2008,
  // use DXGK_ACPI_PASS_ARGS_TO_CHILDREN.

  #if (NTDDI_VERSION &gt;= NTDDI_WIN6SP1)
   AcpiInputBuffer.Signature = 
   DXGK_ACPI_PASS_ARGS_TO_CHILDREN;
     #else
    AcpiInputBuffer.Signature = 
   ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE;
       #endif

     AcpiInputBuffer.MethodNameAsUlong = 
   ACPI_METHOD_OUTPUT_DGS;
     Status = DxgkCbEvalAcpiMethod(HwDeviceExtension-&gt;DeviceHandle,
         ChildUid,
         &amp;AcpiInputBuffer,
         sizeof(ACPI_EVAL_INPUT_BUFFER_COMPLEX),
         &amp;AcpiOutputBuffer,
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
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536116">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/fdefde51-0e90-4324-9c14-e8259fc872b3">DxgkDdiNotifyAcpiEvent</a>



<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>
 

 

