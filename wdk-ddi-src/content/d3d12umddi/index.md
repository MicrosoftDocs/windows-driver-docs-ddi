---
UID: NA:d3d12umddi
ms.assetid: f0332247-492e-3990-bccc-5ec7fc2fd910
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# D3D12Umddi.h header



This header is used by Display. For more information, see
- [Display](../_display/index.md)

D3D12Umddi.h contain these programming interfaces:


## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PFND3D12DDI_ALLOCATE_CB_0022 callback](nc-d3d12umddi-pfnd3d12ddi_allocate_cb_0022.md) | The pfnAllocateCb callback function controls heap allocation by using a D3D12DDICB_ALLOCATE_0022 value. |
| [PFND3D12DDI_BEGIN_END_QUERY_0003 callback](nc-d3d12umddi-pfnd3d12ddi_begin_end_query_0003.md) | The pfnBeginQuery callback function defines the beginning of the portion of a command list to which a query applies. |
| [PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivatecommandqueuesize_0023.md) | The pfnCalcPrivateCommandQueueSize callback function is used to calculate the size of a private command queue. |
| [PFND3D12DDI_CALCPRIVATECRYPTOSESSIONPOLICYSIZE_0030 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivatecryptosessionpolicysize_0030.md) | Used to calculate a session policy size. |
| [PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivatecryptosessionsize_0030.md) | Used to calculate a private session size. |
| [PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONPOLICYSIZE_0030 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivateopenedcryptosessionpolicysize_0030.md) | Used to calculate the size of an opened session policy. |
| [PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONSIZE_0030 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivateopenedcryptosessionsize_0030.md) | Used to calculate the size of an opened session. |
| [PFND3D12DDI_CALCPRIVATEOPENEDPROTECTEDRESOURCESESSIONSIZE_0030 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivateopenedprotectedresourcesessionsize_0030.md) | Used to calculate the size of an opened protected resource session. |
| [PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivateprotectedresourcesessionsize_0030.md) | Used to calculate the size of a protected resource session. |
| [PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0032 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideodecoderheapsize_0032.md) | Used to calculate the size of a video decoder heap. |
| [PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideodecoderheapsize_0033.md) | Used to calculate the size of a video decoder heap. |
| [PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideodecodersize_0021.md) | The pfnCalcPrivateVideoDecoderSize callback function calculates the size of a private video decoder. |
| [PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0032 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideodecodersize_0032.md) | Used to calculate the size of a video decoder. |
| [PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0021 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoprocessorsize_0021.md) | The pfnCalcPrivateVideoProcessorSize callback function calculates the size of the private video processor. |
| [PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032 callback](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoprocessorsize_0032.md) | Used to calculate the size of a video processor. |
| [PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033 callback](nc-d3d12umddi-pfnd3d12ddi_calc_private_pipeline_state_size_0033.md) | Used to calculate the pipeline state size. |
| [PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 callback](nc-d3d12umddi-pfnd3d12ddi_checkexisitingresourceallocationinfo_0022.md) | The pfnCheckExistingResourceAllocationInfo callback function supports checking existing resource allocation information. |
| [PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0022 callback](nc-d3d12umddi-pfnd3d12ddi_checkresourceallocationinfo_0022.md) | The pfnCheckResourceAllocationInfo callback function supports checking resource allocation information. |
| [PFND3D12DDI_CREATECOMMANDQUEUE_0023 callback](nc-d3d12umddi-pfnd3d12ddi_createcommandqueue_0023.md) | The pfnCreateCommandQueue callback function is used to create command queue. |
| [PFND3D12DDI_CREATECRYPTOSESSIONPOLICY_0030 callback](nc-d3d12umddi-pfnd3d12ddi_createcryptosessionpolicy_0030.md) | Used to create a crypto session policy. |
| [PFND3D12DDI_CREATECRYPTOSESSION_0030 callback](nc-d3d12umddi-pfnd3d12ddi_createcryptosession_0030.md) | Used to create a crypto session. |
| [PFND3D12DDI_CREATEDEVICE_0003 callback](nc-d3d12umddi-pfnd3d12ddi_createdevice_0003.md) | The PFND3D12DDI_CREATEDEVICE_0003 function creates a graphics context that is referenced in subsequent calls. |
| [PFND3D12DDI_CREATEHEAPANDRESOURCE_0030 callback](nc-d3d12umddi-pfnd3d12ddi_createheapandresource_0030.md) | Used to simultaneously create a heap and resource. |
| [PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030 callback](nc-d3d12umddi-pfnd3d12ddi_createprotectedresourcesession_0030.md) | Used to create a protected resource session. |
| [PFND3D12DDI_CREATEVIDEODECODERHEAP_0032 callback](nc-d3d12umddi-pfnd3d12ddi_createvideodecoderheap_0032.md) | Used to create a video decoder heap. |
| [PFND3D12DDI_CREATEVIDEODECODERHEAP_0033 callback](nc-d3d12umddi-pfnd3d12ddi_createvideodecoderheap_0033.md) | Used to create a video decoder heap. |
| [PFND3D12DDI_CREATEVIDEODECODER_0021 callback](nc-d3d12umddi-pfnd3d12ddi_createvideodecoder_0021.md) | The pfnCreateVideoDecoder callback function creates a video decoder. |
| [PFND3D12DDI_CREATEVIDEODECODER_0032 callback](nc-d3d12umddi-pfnd3d12ddi_createvideodecoder_0032.md) | Used to create a video decoder. |
| [PFND3D12DDI_CREATEVIDEOPROCESSOR_0021 callback](nc-d3d12umddi-pfnd3d12ddi_createvideoprocessor_0021.md) | The pfnCreateVideoProcessor callback function creates a video processor. |
| [PFND3D12DDI_CREATEVIDEOPROCESSOR_0032 callback](nc-d3d12umddi-pfnd3d12ddi_createvideoprocessor_0032.md) | Used to create a video processor. |
| [PFND3D12DDI_CREATE_PIPELINE_STATE_0021 callback](nc-d3d12umddi-pfnd3d12ddi_create_pipeline_state_0021.md) | The pfnCreatePipelineState callback function creates a pipeline state. |
| [PFND3D12DDI_CREATE_PIPELINE_STATE_0033 callback](nc-d3d12umddi-pfnd3d12ddi_create_pipeline_state_0033.md) | Used to create a pipeline state. |
| [PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 callback](nc-d3d12umddi-pfnd3d12ddi_create_protected_session_cb_0030.md) | Used to create a protected session state. |
| [PFND3D12DDI_DEALLOCATE_CB_0022 callback](nc-d3d12umddi-pfnd3d12ddi_deallocate_cb_0022.md) | The pfnDeallocateCb callback function controls heap deallocation by using a D3D12DDICB_DEALLOCATE_0022 structure. |
| [PFND3D12DDI_DESTROYCRYPTOSESSIONPOLICY_0030 callback](nc-d3d12umddi-pfnd3d12ddi_destroycryptosessionpolicy_0030.md) | Used to destroy a crypto session. |
| [PFND3D12DDI_DESTROYCRYPTOSESSION_0030 callback](nc-d3d12umddi-pfnd3d12ddi_destroycryptosession_0030.md) | Used to destroy a crypto session. |
| [PFND3D12DDI_DESTROYPROTECTEDRESOURCESESSION_0030 callback](nc-d3d12umddi-pfnd3d12ddi_destroyprotectedresourcesession_0030.md) | Used to destroy a protected resource session. |
| [PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032 callback](nc-d3d12umddi-pfnd3d12ddi_destroyvideodecoderheap_0032.md) | Used to destroy a video decoder heap. |
| [PFND3D12DDI_DESTROYVIDEODECODER_0021 callback](nc-d3d12umddi-pfnd3d12ddi_destroyvideodecoder_0021.md) | Destroys the video decoder. |
| [PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021 callback](nc-d3d12umddi-pfnd3d12ddi_destroyvideoprocessor_0021.md) | The pfnDestroyVideoProcessor callback function destroys a video processor. |
| [PFND3D12DDI_GETKEYBASEDATA_0030 callback](nc-d3d12umddi-pfnd3d12ddi_getkeybasedata_0030.md) | Used to get key base data. |
| [PFND3D12DDI_GETPAGEABLESIZE_0020 callback](nc-d3d12umddi-pfnd3d12ddi_getpageablesize_0020.md) | The pfnGetPageableSize callback function gets the pageable size. |
| [PFND3D12DDI_OPENADAPTER callback](nc-d3d12umddi-pfnd3d12ddi_openadapter.md) | The PFND3D12DDI_OPENADAPTER function creates a graphics adapter object that is referenced in subsequent calls. |
| [PFND3D12DDI_OPENCRYPTOSESSIONPOLICY_0030 callback](nc-d3d12umddi-pfnd3d12ddi_opencryptosessionpolicy_0030.md) | Used to open a crypto session policy. |
| [PFND3D12DDI_OPENCRYPTOSESSION_0030 callback](nc-d3d12umddi-pfnd3d12ddi_opencryptosession_0030.md) | Used to open a crypto session. |
| [PFND3D12DDI_OPENPROTECTEDRESOURCESESSION_0030 callback](nc-d3d12umddi-pfnd3d12ddi_openprotectedresourcesession_0030.md) | Used to open a protected resource session. |
| [PFND3D12DDI_RESOLVE_QUERY_DATA callback](nc-d3d12umddi-pfnd3d12ddi_resolve_query_data.md) | The pfnResolveQueryData callback function transforms a previously stored query into an API defined format. |
| [PFND3D12DDI_RESOURCEBARRIER_0022 callback](nc-d3d12umddi-pfnd3d12ddi_resourcebarrier_0022.md) | The pfnResourceBarrier callback function supports resource barriers. |
| [PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030 callback](nc-d3d12umddi-pfnd3d12ddi_setprotectedresourcesession_0030.md) | Used to set a protected resource session. |
| [PFND3D12DDI_SETVIEWINSTANCEMASK_0033 callback](nc-d3d12umddi-pfnd3d12ddi_setviewinstancemask_0033.md) | Used to set a view instance mask. |
| [PFND3D12DDI_SET_EXTENDED_FEATURE_CALLBACKS_0021 callback](nc-d3d12umddi-pfnd3d12ddi_set_extended_feature_callbacks_0021.md) | The pfnSetExtendedFeatureCallbacks callback function sets extended feature callbacks. |
| [PFND3D12DDI_SET_PREDICATION callback](nc-d3d12umddi-pfnd3d12ddi_set_predication.md) | The pfnSetPredication callback function denotes that subsequent video operations and resource manipulation commands are not actually performed if the resulting predicate data of the predicate is equal to the operation specified. |
| [PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021 callback](nc-d3d12umddi-pfnd3d12ddi_shadercachegetvalue_cb_0021.md) | The pfnShaderCacheGetValueCb callback function gets a shader cache value. |
| [PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 callback](nc-d3d12umddi-pfnd3d12ddi_shadercachestorevalue_cb_0021.md) | The pfnShaderCacheStoreValueCb callback function stores a shader cache value. |
| [PFND3D12DDI_TRANSFORMENCRYPTEDDATA_0030 callback](nc-d3d12umddi-pfnd3d12ddi_transformencrypteddata_0030.md) | Used to transform encrypted data. |
| [PFND3D12DDI_VIDEO_DECODER_TRIM_ALLOCATIONS_0021 callback](nc-d3d12umddi-pfnd3d12ddi_video_decoder_trim_allocations_0021.md) | The pfnDecoderTrimAllocations callback function trims allocations for submissions that are finished. |
| [PFND3D12DDI_VIDEO_DECODE_FRAME_0021 callback](nc-d3d12umddi-pfnd3d12ddi_video_decode_frame_0021.md) | The pfnDecodeFrame callback function records a decode frame operation to the command list. |
| [PFND3D12DDI_VIDEO_DECODE_FRAME_0030 callback](nc-d3d12umddi-pfnd3d12ddi_video_decode_frame_0030.md) | Used to decode a video frame. |
| [PFND3D12DDI_VIDEO_DECODE_FRAME_0032 callback](nc-d3d12umddi-pfnd3d12ddi_video_decode_frame_0032.md) | Used to decode a video frame. |
| [PFND3D12DDI_VIDEO_GETCAPS callback](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md) | The pfnGetCaps callback function defines an entry point for video specific caps. |
| [PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 callback](nc-d3d12umddi-pfnd3d12ddi_video_get_bitstream_encryption_scheme_count_0020.md) | The pfnGetBitstreamEncryptionSchemeCount callback function retrieves the number of encryption schemes supported for a decode profile. |
| [PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020 callback](nc-d3d12umddi-pfnd3d12ddi_video_get_decode_format_count_0020.md) | The pfnGetDecodeFormatCount callback function retrieves the number of formats supported for a decode configuration. |
| [PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020 callback](nc-d3d12umddi-pfnd3d12ddi_video_get_decode_profile_count_0020.md) | The pfnGetDecodeProfileCount callback function retrieves the number of decode profiles supported by the driver. |
| [PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021 callback](nc-d3d12umddi-pfnd3d12ddi_video_processor_trim_allocations_0021.md) | The pfnProcessorTrimAllocations callback function trims allocations for submissions that are finished. |
| [PFND3D12DDI_VIDEO_PROCESS_FRAME_0021 callback](nc-d3d12umddi-pfnd3d12ddi_video_process_frame_0021.md) | The pfnProcessFrame callback function performs a video processing operation on one or more input samples and writes the result to an output surface. |
| [PFND3D12DDI_VIDEO_PROCESS_FRAME_0032 callback](nc-d3d12umddi-pfnd3d12ddi_video_process_frame_0032.md) | Used to process a video frame. |
| [PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032 callback](nc-d3d12umddi-pfnd3d12ddi_writebufferimmediate_0032.md) | Used to create a write buffer. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [D3D12DDIARG_CREATECOMMANDQUEUE_0023 structure](ns-d3d12umddi-d3d12ddiarg_createcommandqueue_0023.md) | Contains arguments used to create a command queue. |
| [D3D12DDIARG_CREATEDEVICE_0003 structure](ns-d3d12umddi-d3d12ddiarg_createdevice_0003.md) | The D3D10DDIARG_CREATEDEVICE_0003 structure describes the display device to create. |
| [D3D12DDIARG_CREATE_CRYPTO_SESSION_0030 structure](ns-d3d12umddi-d3d12ddiarg_create_crypto_session_0030.md) | Creates a crypto session. |
| [D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030 structure](ns-d3d12umddi-d3d12ddiarg_create_crypto_session_policy_0030.md) | Creates a crypto session policy. |
| [D3D12DDIARG_CREATE_PIPELINE_STATE_0033 structure](ns-d3d12umddi-d3d12ddiarg_create_pipeline_state_0033.md) | Creates a pipeline state. |
| [D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030 structure](ns-d3d12umddi-d3d12ddiarg_create_protected_resource_session_0030.md) | Creates a protected resource session. |
| [D3D12DDIARG_CREATE_VIDEO_DECODER_0021 structure](ns-d3d12umddi-d3d12ddiarg_create_video_decoder_0021.md) | Used to create a decoder object for a decode session. |
| [D3D12DDIARG_CREATE_VIDEO_DECODER_0032 structure](ns-d3d12umddi-d3d12ddiarg_create_video_decoder_0032.md) | Creates a video decoder. |
| [D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032 structure](ns-d3d12umddi-d3d12ddiarg_create_video_decoder_heap_0032.md) | Creates a video decoder heap. |
| [D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033 structure](ns-d3d12umddi-d3d12ddiarg_create_video_decoder_heap_0033.md) | Create a video decoder heap. |
| [D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021 structure](ns-d3d12umddi-d3d12ddiarg_create_video_processor_0021.md) | Specifies arguments used to create a video processor. |
| [D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032 structure](ns-d3d12umddi-d3d12ddiarg_create_video_processor_0032.md) | Creates a video processor. |
| [D3D12DDIARG_GET_PAGEABLE_SIZE_0020 structure](ns-d3d12umddi-d3d12ddiarg_get_pageable_size_0020.md) | Specifies information used to get the driver reported size for an array of allocations. |
| [D3D12DDIARG_OPENADAPTER structure](ns-d3d12umddi-d3d12ddiarg_openadapter.md) | The D3D12DDIARG_OPENADAPTER structure describes the graphics adapter object. |
| [D3D12DDIARG_OPEN_CRYPTO_SESSION_0030 structure](ns-d3d12umddi-d3d12ddiarg_open_crypto_session_0030.md) | Opens a crypto session. |
| [D3D12DDIARG_OPEN_CRYPTO_SESSION_POLICY_0030 structure](ns-d3d12umddi-d3d12ddiarg_open_crypto_session_policy_0030.md) | Opens a crypto session policy. |
| [D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030 structure](ns-d3d12umddi-d3d12ddiarg_open_protected_resource_session_0030.md) | Opens a protected resource session. |
| [D3D12DDIARG_RESOURCE_BARRIER_0022 structure](ns-d3d12umddi-d3d12ddiarg_resource_barrier_0022.md) | Describes a resource barrier. |
| [D3D12DDIARG_VIDEO_GETCAPS_0020 structure](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md) | Specifies values used to get capabilities of a type. |
| [D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0020 structure](ns-d3d12umddi-d3d12ddiarg_video_process_input_stream_arguments_0020.md) | Specifies input stream parameters for an input stream passed to the pfnProcessFrame callback function. |
| [D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0032 structure](ns-d3d12umddi-d3d12ddiarg_video_process_input_stream_arguments_0032.md) | The video process input stream arguments. |
| [D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0020 structure](ns-d3d12umddi-d3d12ddiarg_video_process_output_stream_arguments_0020.md) | Specifies output stream parameters for the output to be processed. |
| [D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032 structure](ns-d3d12umddi-d3d12ddiarg_video_process_output_stream_arguments_0032.md) | The video process output stream arguments. |
| [D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023 structure](ns-d3d12umddi-d3d12ddicaps_umd_based_command_queue_priority_data_0023.md) | Contains priority data for a user-mode driver (UMD)-based command queue. |
| [D3D12DDICB_ALLOCATE_0022 structure](ns-d3d12umddi-d3d12ddicb_allocate_0022.md) | Specifies information for use in an allocation callback function. |
| [D3D12DDICB_DEALLOCATE_0022 structure](ns-d3d12umddi-d3d12ddicb_deallocate_0022.md) | Specifies values for use with a deallocation callback function. |
| [D3D12DDI_ALLOCATION_INFO_0022 structure](ns-d3d12umddi-d3d12ddi_allocation_info_0022.md) | Specifies allocation information. |
| [D3D12DDI_COMMAND_LIST_FUNCS_3D_0030 structure](ns-d3d12umddi-d3d12ddi_command_list_funcs_3d_0030.md) | The command list functions for 3D. |
| [D3D12DDI_COMMAND_LIST_FUNCS_3D_0032 structure](ns-d3d12umddi-d3d12ddi_command_list_funcs_3d_0032.md) | The command list functions for 3D. |
| [D3D12DDI_COMMAND_LIST_FUNCS_3D_0033 structure](ns-d3d12umddi-d3d12ddi_command_list_funcs_3d_0033.md) | The command list functions for 3D. |
| [D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0030 structure](ns-d3d12umddi-d3d12ddi_command_list_funcs_video_decode_0030.md) | Command list functions for video decode. |
| [D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_DECODE_0032 structure](ns-d3d12umddi-d3d12ddi_command_list_funcs_video_decode_0032.md) | Command list functions for video decode. |
| [D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0030 structure](ns-d3d12umddi-d3d12ddi_command_list_funcs_video_process_0030.md) | Command list functions for video process. |
| [D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0032 structure](ns-d3d12umddi-d3d12ddi_command_list_funcs_video_process_0032.md) | The command list functions for video processing. |
| [D3D12DDI_COMMAND_QUEUE_FUNCS_VIDEO_0020 structure](ns-d3d12umddi-d3d12ddi_command_queue_funcs_video_0020.md) | Command queue functions for video. |
| [D3D12DDI_CONTENT_PROTECTION_CALLBACKS_0030 structure](ns-d3d12umddi-d3d12ddi_content_protection_callbacks_0030.md) | Content protection callbacks. |
| [D3D12DDI_CORELAYER_DEVICECALLBACKS_0022 structure](ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022.md) | This structure contains runtime callback functions that the user-mode display driver can use. |
| [D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030 structure](ns-d3d12umddi-d3d12ddi_crypto_session_transform_decrypt_header_input_arguments_0030.md) | Crypto session transform decrypt header input arguments. |
| [D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_OUTPUT_ARGUMENTS_0030 structure](ns-d3d12umddi-d3d12ddi_crypto_session_transform_decrypt_header_output_arguments_0030.md) | Crypto session transform decrypt header output arguments. |
| [D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_OUTPUT_ARGUMENTS_0030 structure](ns-d3d12umddi-d3d12ddi_crypto_session_transform_decrypt_output_arguments_0030.md) | Crypt session transform decrypt output arguments. |
| [D3D12DDI_CRYPTO_SESSION_TRANSFORM_INPUT_ARGUMENTS_0030 structure](ns-d3d12umddi-d3d12ddi_crypto_session_transform_input_arguments_0030.md) | Crypto session transform input arguments. |
| [D3D12DDI_CRYPTO_SESSION_TRANSFORM_OUTPUT_ARGUMENTS_0030 structure](ns-d3d12umddi-d3d12ddi_crypto_session_transform_output_arguments_0030.md) | Crypto session transform output arguments. |
| [D3D12DDI_CRYPTO_SESSION_TRANSFORM_TRANSCRYPT_OUTPUT_ARGUMENTS_0030 structure](ns-d3d12umddi-d3d12ddi_crypto_session_transform_transcrypt_output_arguments_0030.md) | Crypto session transform transcrypt output arguments. |
| [D3D12DDI_D3D12_OPTIONS_DATA_0031 structure](ns-d3d12umddi-d3d12ddi_d3d12_options_data_0031.md) | Display options data. |
| [D3D12DDI_D3D12_OPTIONS_DATA_0032 structure](ns-d3d12umddi-d3d12ddi_d3d12_options_data_0032.md) | Display options data. |
| [D3D12DDI_D3D12_OPTIONS_DATA_0033 structure](ns-d3d12umddi-d3d12ddi_d3d12_options_data_0033.md) | Display options data. |
| [D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030 structure](ns-d3d12umddi-d3d12ddi_device_funcs_content_protection_streaming_0030.md) | Device function for content protection streaming. |
| [D3D12DDI_DEVICE_FUNCS_CORE_0010 structure](ns-d3d12umddi-d3d12ddi_device_funcs_core_0010.md) | Contains core functions. |
| [D3D12DDI_DEVICE_FUNCS_CORE_0021 structure](ns-d3d12umddi-d3d12ddi_device_funcs_core_0021.md) | Specifies core device functions. |
| [D3D12DDI_DEVICE_FUNCS_CORE_0030 structure](ns-d3d12umddi-d3d12ddi_device_funcs_core_0030.md) | Core device functions. |
| [D3D12DDI_DEVICE_FUNCS_CORE_0033 structure](ns-d3d12umddi-d3d12ddi_device_funcs_core_0033.md) | Core device functions. |
| [D3D12DDI_DEVICE_FUNCS_CORE_VIDEO_0020 structure](ns-d3d12umddi-d3d12ddi_device_funcs_core_video_0020.md) | This structure contains device functions for core features in video. |
| [D3D12DDI_DEVICE_FUNCS_VIDEO_0021 structure](ns-d3d12umddi-d3d12ddi_device_funcs_video_0021.md) | Contains video functions. |
| [D3D12DDI_DEVICE_FUNCS_VIDEO_0030 structure](ns-d3d12umddi-d3d12ddi_device_funcs_video_0030.md) | Video device functions. |
| [D3D12DDI_DEVICE_FUNCS_VIDEO_0032 structure](ns-d3d12umddi-d3d12ddi_device_funcs_video_0032.md) | Video device functions. |
| [D3D12DDI_DEVICE_FUNCS_VIDEO_0033 structure](ns-d3d12umddi-d3d12ddi_device_funcs_video_0033.md) | The device functions of video. |
| [D3D12DDI_EXTENDED_FEATURES_FUNCS_0020 structure](ns-d3d12umddi-d3d12ddi_extended_features_funcs_0020.md) | This structure contains device functions for extended features in video. |
| [D3D12DDI_EXTENDED_FEATURES_FUNCS_0021 structure](ns-d3d12umddi-d3d12ddi_extended_features_funcs_0021.md) | Specifies callback functions for extended features. |
| [D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_DATA_0030 structure](ns-d3d12umddi-d3d12ddi_protected_resource_session_support_data_0030.md) | Protected resource session support data. |
| [D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022 structure](ns-d3d12umddi-d3d12ddi_query_data_video_decode_statistics_0022.md) | Video decode statistics for a query. |
| [D3D12DDI_RANGE structure](ns-d3d12umddi-d3d12ddi_range.md) | Specifies a range. |
| [D3D12DDI_RESOURCE_ALLOCATION_INFO_0022 structure](ns-d3d12umddi-d3d12ddi_resource_allocation_info_0022.md) | Specifies information for resource allocation. |
| [D3D12DDI_RESOURCE_RANGED_BARRIER_0022 structure](ns-d3d12umddi-d3d12ddi_resource_ranged_barrier_0022.md) | Describes a resource ranged barrier. |
| [D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003 structure](ns-d3d12umddi-d3d12ddi_resource_transition_barrier_0003.md) | Describes a transition barrier between subresources. |
| [D3D12DDI_RESOURCE_UAV_BARRIER structure](ns-d3d12umddi-d3d12ddi_resource_uav_barrier.md) | Contains an unordered access view (UAV) barrier. |
| [D3D12DDI_SHADERCACHE_CALLBACKS_0021 structure](ns-d3d12umddi-d3d12ddi_shadercache_callbacks_0021.md) | Specifies shader cache callback functions. |
| [D3D12DDI_SHADERCACHE_HASH structure](ns-d3d12umddi-d3d12ddi_shadercache_hash.md) | Includes a hash value. |
| [D3D12DDI_SWIZZLE_BIT_ENTRY structure](ns-d3d12umddi-d3d12ddi_swizzle_bit_entry.md) | Defines a swizzle bit entry. |
| [D3D12DDI_SWIZZLE_PATTERN_DESC_0022 structure](ns-d3d12umddi-d3d12ddi_swizzle_pattern_desc_0022.md) | Describes a swizzle pattern. |
| [D3D12DDI_TEXTURE_LAYOUT_CAPS_0001 structure](ns-d3d12umddi-d3d12ddi_texture_layout_caps_0001.md) | Specifies texture layout capabilities. |
| [D3D12DDI_TEXTURE_LAYOUT_CAPS_0026 structure](ns-d3d12umddi-d3d12ddi_texture_layout_caps_0026.md) | Specifies texture layout capabilities. |
| [D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_COUNT_DATA_0030 structure](ns-d3d12umddi-d3d12ddi_video_content_protection_system_count_data_0030.md) | Video content protection system count data. |
| [D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030 structure](ns-d3d12umddi-d3d12ddi_video_content_protection_system_support_data_0030.md) | Video content protection system support data. |
| [D3D12DDI_VIDEO_CRYPTO_SESSION_SUPPORT_DATA_0030 structure](ns-d3d12umddi-d3d12ddi_video_crypto_session_support_data_0030.md) | Video crypto session support data. |
| [D3D12DDI_VIDEO_CRYPTO_SESSION_TRANSFORM_SUPPORT_DATA_0030 structure](ns-d3d12umddi-d3d12ddi_video_crypto_session_transform_support_data_0030.md) | Video crypto session transform support data. |
| [D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0032 structure](ns-d3d12umddi-d3d12ddi_video_decoder_heap_size_data_0032.md) | Data structure for the D3D12DDICAPS_TYPE_VIDEO_0032_DECODER_HEAP_SIZE capability check. Retrieves the memory allocation size of a video decoder heap created with the given properties. |
| [D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033 structure](ns-d3d12umddi-d3d12ddi_video_decoder_heap_size_data_0033.md) | The video decoder heap size data. |
| [D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA_0020 structure](ns-d3d12umddi-d3d12ddi_video_decode_bitstream_encryption_schemes_data_0020.md) | Specifies information used to retrieve the bitstream encryption schemes supported for a decode profile. |
| [D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT_DATA_0032 structure](ns-d3d12umddi-d3d12ddi_video_decode_bitstream_encryption_scheme_count_data_0032.md) | Video decode bitstream encryption scheme count data. |
| [D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020 structure](ns-d3d12umddi-d3d12ddi_video_decode_compressed_bitstream_0020.md) | Contains the compressed bitstream from which to decode. |
| [D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0032 structure](ns-d3d12umddi-d3d12ddi_video_decode_compressed_bitstream_0032.md) | Video decode compressed bitstream. |
| [D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020 structure](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md) | Includes information about the video decode configuration. |
| [D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0021 structure](ns-d3d12umddi-d3d12ddi_video_decode_conversion_arguments_0021.md) | Specifies the arguments for decode output conversion. |
| [D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022 structure](ns-d3d12umddi-d3d12ddi_video_decode_conversion_support_data_0022.md) | Specifies information used to check whether a color space conversion, format conversion, and scale are supported and whether it is required for real-time reasons or reference buffer format. |
| [D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032 structure](ns-d3d12umddi-d3d12ddi_video_decode_conversion_support_data_0032.md) | Video decode conversion support data. |
| [D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030 structure](ns-d3d12umddi-d3d12ddi_video_decode_decryption_arguments_0030.md) | Video decode decryption arguments. |
| [D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020 structure](ns-d3d12umddi-d3d12ddi_video_decode_formats_data_0020.md) | Specifies information used to retrieve a list of supported formats for a decode configuration. |
| [D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032 structure](ns-d3d12umddi-d3d12ddi_video_decode_format_count_data_0032.md) | Video decode format count data. |
| [D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020 structure](ns-d3d12umddi-d3d12ddi_video_decode_frame_argument_0020.md) | Contains the decode parameters for the frame. |
| [D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020 structure](ns-d3d12umddi-d3d12ddi_video_decode_input_stream_arguments_0020.md) | Specifies input stream arguments. |
| [D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0030 structure](ns-d3d12umddi-d3d12ddi_video_decode_input_stream_arguments_0030.md) | Video decode input stream arguments. |
| [D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032 structure](ns-d3d12umddi-d3d12ddi_video_decode_input_stream_arguments_0032.md) | Video decode input stream arguments. |
| [D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0021 structure](ns-d3d12umddi-d3d12ddi_video_decode_output_stream_arguments_0021.md) | Output stream arguments for video decode. |
| [D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020 structure](ns-d3d12umddi-d3d12ddi_video_decode_profiles_data_0020.md) | Specifies information used to retrieve a list of profiles. |
| [D3D12DDI_VIDEO_DECODE_PROFILE_COUNT_DATA_0032 structure](ns-d3d12umddi-d3d12ddi_video_decode_profile_count_data_0032.md) | Video decode profile count data. |
| [D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0020 structure](ns-d3d12umddi-d3d12ddi_video_decode_reference_frames_0020.md) | Contains the reference frames for the current decode operation. |
| [D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032 structure](ns-d3d12umddi-d3d12ddi_video_decode_reference_frames_0032.md) | Video decode reference frames. |
| [D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 structure](ns-d3d12umddi-d3d12ddi_video_decode_support_data_0020.md) | Specifies data used to determine support of hardware for a configuration. |
| [D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020 structure](ns-d3d12umddi-d3d12ddi_video_format_description_0020.md) | Defines the combination of a pixel format and color space for a resource content description. |
| [D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032 structure](ns-d3d12umddi-d3d12ddi_video_processor_input_stream_desc_0032.md) | Describes input stream properties for the video processor. |
| [D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0032 structure](ns-d3d12umddi-d3d12ddi_video_processor_size_data_0032.md) | Data structure for the D3D12DDICAPS_TYPE_VIDEO_0032_PROCESSOR_SIZE capability check. Retrieves the memory allocation size of a video processor created with the given properties. |
| [D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020 structure](ns-d3d12umddi-d3d12ddi_video_process_alpha_blending_0020.md) | Specifies whether alpha blending is enabled and, if so, the planar alpha value. |
| [D3D12DDI_VIDEO_PROCESS_FILTER_RANGE_0020 structure](ns-d3d12umddi-d3d12ddi_video_process_filter_range_0020.md) | Defines the range of supported values for an image filter. |
| [D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020 structure](ns-d3d12umddi-d3d12ddi_video_process_input_stream_0020.md) | Contains stream information for the video processor blend functionality. |
| [D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020 structure](ns-d3d12umddi-d3d12ddi_video_process_input_stream_rate_info_0020.md) | Information for the input stream rate to use for video processing in a pattern, such as deinterlacing or frame-rate conversion. |
| [D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032 structure](ns-d3d12umddi-d3d12ddi_video_process_input_stream_rate_info_0032.md) | The video process input stream rate info. |
| [D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020 structure](ns-d3d12umddi-d3d12ddi_video_process_luma_key_0020.md) | Specifies values for luma keying. |
| [D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020 structure](ns-d3d12umddi-d3d12ddi_video_process_max_input_streams_data_0020.md) | Specifies information used to retrieve the maximum number of input data streams that can be enabled for a video processor. |
| [D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020 structure](ns-d3d12umddi-d3d12ddi_video_process_output_stream_0020.md) | The output stream for video processing commands, which points to a target surface. |
| [D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032 structure](ns-d3d12umddi-d3d12ddi_video_process_output_stream_desc_0032.md) | Describes output stream properties for the video processor. |
| [D3D12DDI_VIDEO_PROCESS_PALETTE_0020 structure](ns-d3d12umddi-d3d12ddi_video_process_palette_0020.md) | Specifies whether the palette is enabled and an array of palette entries. |
| [D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020 structure](ns-d3d12umddi-d3d12ddi_video_process_references_info_0020.md) | Contains the reference frames needed to perform video processing. |
| [D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020 structure](ns-d3d12umddi-d3d12ddi_video_process_reference_info_data_0020.md) | Data structure for D3D12DDICAPS_VIDEO_PROCESS_REFERENCE_INFO capability check. Retrieves the number of past and future frames required for a given deinterlace mode. |
| [D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022 structure](ns-d3d12umddi-d3d12ddi_video_process_support_data_0022.md) | Specifies information used to retrieve capabilities for a video processor. |
| [D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032 structure](ns-d3d12umddi-d3d12ddi_video_process_support_data_0032.md) | Video process support data. |
| [D3D12DDI_VIDEO_PROCESS_TRANSFORM_0020 structure](ns-d3d12umddi-d3d12ddi_video_process_transform_0020.md) | Contains information for a transform. |
| [D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032 structure](ns-d3d12umddi-d3d12ddi_video_process_transform_0032.md) | Video process transform. |
| [D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020 structure](ns-d3d12umddi-d3d12ddi_video_sample_description_0020.md) | Describes the width, height, format, and color space of a picture buffer. |
| [D3D12DDI_VIDEO_SCALE_SUPPORT_0022 structure](ns-d3d12umddi-d3d12ddi_video_scale_support_0022.md) | Describes a supported range of output sizes for a scaler. |
| [D3D12DDI_VIDEO_SCALE_SUPPORT_0032 structure](ns-d3d12umddi-d3d12ddi_video_scale_support_0032.md) | Video scale support. |
| [D3D12DDI_VIDEO_SIZE_RANGE_0032 structure](ns-d3d12umddi-d3d12ddi_video_size_range_0032.md) | Video size range. |
| [D3D12DDI_VIEW_INSTANCE_LOCATION structure](ns-d3d12umddi-d3d12ddi_view_instance_location.md) | View instance location. |
| [D3D12DDI_VIEW_INSTANCING_DESC structure](ns-d3d12umddi-d3d12ddi_view_instancing_desc.md) | View instancing description. |
| [D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032 structure](ns-d3d12umddi-d3d12ddi_writebufferimmediate_parameter_0032.md) | Write buffer immediate parameter. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [D3D12DDICAPS_TYPE enumeration](ne-d3d12umddi-d3d12ddicaps_type.md) | Specifies a capability type. |
| [D3D12DDICAPS_TYPE_VIDEO_0020 enumeration](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md) | Contains capability types for video. |
| [D3D12DDI_ALLOCATION_INFO_FLAGS_0022 enumeration](ne-d3d12umddi-d3d12ddi_allocation_info_flags_0022.md) | Contains allocation information flags. |
| [D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030 enumeration](ne-d3d12umddi-d3d12ddi_bitstream_encryption_type_0030.md) | The bitstream encryption type. |
| [D3D12DDI_COMMAND_QUEUE_CREATION_FLAGS enumeration](ne-d3d12umddi-d3d12ddi_command_queue_creation_flags.md) | Defines command queue creation options. |
| [D3D12DDI_COMMAND_QUEUE_FLAGS enumeration](ne-d3d12umddi-d3d12ddi_command_queue_flags.md) | Contains values for the video command queue. |
| [D3D12DDI_CREATE_SHADER_FLAGS enumeration](ne-d3d12umddi-d3d12ddi_create_shader_flags.md) | Defines flags for shader creation. |
| [D3D12DDI_CRYPTO_SESSION_FLAGS_0030 enumeration](ne-d3d12umddi-d3d12ddi_crypto_session_flags_0030.md) | The crypto session flags. |
| [D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030 enumeration](ne-d3d12umddi-d3d12ddi_crypto_session_support_flags_0030.md) | The crypto session support flags. |
| [D3D12DDI_CRYPTO_SESSION_TRANSFORM_OPERATION_0030 enumeration](ne-d3d12umddi-d3d12ddi_crypto_session_transform_operation_0030.md) | The crypto session transform operations. |
| [D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAGS_0030 enumeration](ne-d3d12umddi-d3d12ddi_crypto_session_transform_support_flags_0030.md) | The crypto session transform support flags. |
| [D3D12DDI_DEALLOCATE_FLAGS_0022 enumeration](ne-d3d12umddi-d3d12ddi_deallocate_flags_0022.md) | Defines flags for use in deallocation. |
| [D3D12DDI_FEATURE_0020 enumeration](ne-d3d12umddi-d3d12ddi_feature_0020.md) | Contains available features. |
| [D3D12DDI_HANDLETYPE enumeration](ne-d3d12umddi-d3d12ddi_handletype.md) | Contains driver handle types. |
| [D3D12DDI_HEAP_FLAGS enumeration](ne-d3d12umddi-d3d12ddi_heap_flags.md) | Contains Direct3D 12 heap flags. |
| [D3D12DDI_PREDICATION_OP enumeration](ne-d3d12umddi-d3d12ddi_predication_op.md) | Contains values for predication operation options. |
| [D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAGS_0030 enumeration](ne-d3d12umddi-d3d12ddi_protected_resource_session_support_flags_0030.md) | The protected resource session support flags. |
| [D3D12DDI_QUERY_HEAP_TYPE enumeration](ne-d3d12umddi-d3d12ddi_query_heap_type.md) | Type of a query heap, which is an array of query results. |
| [D3D12DDI_QUERY_TYPE enumeration](ne-d3d12umddi-d3d12ddi_query_type.md) | Type of a query. |
| [D3D12DDI_RESOURCE_BARRIER_FLAGS enumeration](ne-d3d12umddi-d3d12ddi_resource_barrier_flags.md) | Contains resource barrier flags. |
| [D3D12DDI_RESOURCE_BARRIER_TYPE enumeration](ne-d3d12umddi-d3d12ddi_resource_barrier_type.md) | Specifies the type of resource barrier. |
| [D3D12DDI_RESOURCE_FLAGS_0003 enumeration](ne-d3d12umddi-d3d12ddi_resource_flags_0003.md) | Specifies resource flag values. |
| [D3D12DDI_RESOURCE_STATES enumeration](ne-d3d12umddi-d3d12ddi_resource_states.md) | Contains resource states. |
| [D3D12DDI_SWIZZLE_PATTERN enumeration](ne-d3d12umddi-d3d12ddi_swizzle_pattern.md) | Specifies a swizzle pattern. |
| [D3D12DDI_SWIZZLE_PATTERN_FLAGS enumeration](ne-d3d12umddi-d3d12ddi_swizzle_pattern_flags.md) | Specifies swizzle pattern flags. |
| [D3D12DDI_TABLE_TYPE enumeration](ne-d3d12umddi-d3d12ddi_table_type.md) | Command list and queue types to allow drivers to point to different implementations for video. |
| [D3D12DDI_TEXTURE_LAYOUT enumeration](ne-d3d12umddi-d3d12ddi_texture_layout.md) | Specifies a texture layout. |
| [D3D12DDI_VIDEO_CODED_INTERLACE_TYPE_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_coded_interlace_type_0020.md) | Indicates whether the compressed stream contains only frames (PROGRESSIVE_ONLY) or may contain a mix of progressive and interlaced frames (FIELDS). |
| [D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md) | Contains video decode configuration flags. |
| [D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_decode_conversion_support_flags_0020.md) | Contains flags for support of video decode conversion. |
| [D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_decode_parameter_type_0020.md) | Contains the video decode parameter type. |
| [D3D12DDI_VIDEO_DECODE_STATUS_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_decode_status_0020.md) | Contains status values for video decode. |
| [D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_decode_support_flags_0020.md) | Contains video decode support flags. |
| [D3D12DDI_VIDEO_DECODE_TIER_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_decode_tier_0020.md) | Specifies the video decode tier. |
| [D3D12DDI_VIDEO_FIELD_TYPE_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_field_type_0020.md) | Contains values that define how a video frame is interlaced. |
| [D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_frame_stereo_format_0020.md) | Defines the layout in memory of a stereo 3D video frame. |
| [D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_process_alpha_fill_mode_0020.md) | Contains values for alpha fill modes. |
| [D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022 enumeration](ne-d3d12umddi-d3d12ddi_video_process_auto_processing_flags_0022.md) | Contains values for automatic processing for a driver. |
| [D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_process_deinterlace_flags_0020.md) | Defines the deinterlacing video processor capabilities. |
| [D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_process_feature_support_flags_0020.md) | Defines the features that video processor supports. |
| [D3D12DDI_VIDEO_PROCESS_FILTER_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_process_filter_0020.md) | Contains video process filters. |
| [D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020.md) | Defines the image filter capabilities for a video processor. |
| [D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_process_input_stream_flags_0020.md) | Input stream flags. |
| [D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020 enumeration](ne-d3d12umddi-d3d12ddi_video_process_orientation_0020.md) | The orientation to be performed by the video processor. |
| [D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022 enumeration](ne-d3d12umddi-d3d12ddi_video_process_support_flags_0022.md) | Contains values that specify whether the conversion from the source format and color space to destination format and color space is supported. |
| [D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022 enumeration](ne-d3d12umddi-d3d12ddi_video_scale_support_flags_0022.md) | Contains the options for video scale support. |
| [D3D12DDI_VIDEO_USAGE enumeration](ne-d3d12umddi-d3d12ddi_video_usage.md) | A hint for the graphics driver to optimize for different scenarios. |
| [D3D12DDI_VIEW_INSTANCING_FLAGS enumeration](ne-d3d12umddi-d3d12ddi_view_instancing_flags.md) | Defines the view instancing flags. |
| [D3D12DDI_VIEW_INSTANCING_TIER enumeration](ne-d3d12umddi-d3d12ddi_view_instancing_tier.md) | Defines the view instancing tier. |
| [D3D12DDI_WRITEBUFFERIMMEDIATE_MODE_0032 enumeration](ne-d3d12umddi-d3d12ddi_writebufferimmediate_mode_0032.md) | The write buffer immediate mode. |
