---
UID: NE:d3d9types._D3DSHADER_INSTRUCTION_OPCODE_TYPE
title: "_D3DSHADER_INSTRUCTION_OPCODE_TYPE"
author: windows-driver-content
description: This section lists the operation codes that can be contained in the first 16 bits (0 - 15) of an Instruction Token. The sections that follow describe the token format of the instructions that correspond to the operation codes.
old-location: display\shader_operation_codes.htm
tech.root: display
ms.assetid: 58a34fe6-6e63-4022-81b5-2bfc10a75372
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DSHADER_INSTRUCTION_OPCODE_TYPE, D3DSHADER_INSTRUCTION_OPCODE_TYPE enumeration [Display Devices], D3DSIO_ABS, D3DSIO_ADD, D3DSIO_BEM, D3DSIO_BREAK, D3DSIO_BREAKC, D3DSIO_BREAKP, D3DSIO_CALL, D3DSIO_CALLNZ, D3DSIO_CMP, D3DSIO_CND, D3DSIO_COMMENT, D3DSIO_CRS, D3DSIO_DCL, D3DSIO_DEF, D3DSIO_DEFB, D3DSIO_DEFI, D3DSIO_DP2ADD, D3DSIO_DP3, D3DSIO_DP4, D3DSIO_DST, D3DSIO_DSX, D3DSIO_DSY, D3DSIO_ELSE, D3DSIO_END, D3DSIO_ENDIF, D3DSIO_ENDLOOP, D3DSIO_ENDREP, D3DSIO_EXP, D3DSIO_EXPP, D3DSIO_FORCE_DWORD, D3DSIO_FRC, D3DSIO_IF, D3DSIO_IFC, D3DSIO_LABEL, D3DSIO_LIT, D3DSIO_LOG, D3DSIO_LOGP, D3DSIO_LOOP, D3DSIO_LRP, D3DSIO_M3x2, D3DSIO_M3x3, D3DSIO_M3x4, D3DSIO_M4x3, D3DSIO_M4x4, D3DSIO_MAD, D3DSIO_MAX, D3DSIO_MIN, D3DSIO_MOV, D3DSIO_MOVA, D3DSIO_MUL, D3DSIO_NOP, D3DSIO_NRM, D3DSIO_PHASE, D3DSIO_POW, D3DSIO_RCP, D3DSIO_REP, D3DSIO_RET, D3DSIO_RSQ, D3DSIO_SETP, D3DSIO_SGE, D3DSIO_SGN, D3DSIO_SINCOS, D3DSIO_SLT, D3DSIO_SUB, D3DSIO_TEX, D3DSIO_TEXBEM, D3DSIO_TEXBEML, D3DSIO_TEXCOORD, D3DSIO_TEXDEPTH, D3DSIO_TEXDP3, D3DSIO_TEXDP3TEX, D3DSIO_TEXKILL, D3DSIO_TEXLDD, D3DSIO_TEXLDL, D3DSIO_TEXM3x2DEPTH, D3DSIO_TEXM3x2PAD, D3DSIO_TEXM3x2TEX, D3DSIO_TEXM3x3, D3DSIO_TEXM3x3PAD, D3DSIO_TEXM3x3SPEC, D3DSIO_TEXM3x3TEX, D3DSIO_TEXM3x3VSPEC, D3DSIO_TEXREG2AR, D3DSIO_TEXREG2GB, D3DSIO_TEXREG2RGB, UserModeDisplayDriver_Shader_a344517d-f568-4577-9ef2-cd7c11cb471c.xml, _D3DSHADER_INSTRUCTION_OPCODE_TYPE, d3d9types/D3DSHADER_INSTRUCTION_OPCODE_TYPE, d3d9types/D3DSIO_ABS, d3d9types/D3DSIO_ADD, d3d9types/D3DSIO_BEM, d3d9types/D3DSIO_BREAK, d3d9types/D3DSIO_BREAKC, d3d9types/D3DSIO_BREAKP, d3d9types/D3DSIO_CALL, d3d9types/D3DSIO_CALLNZ, d3d9types/D3DSIO_CMP, d3d9types/D3DSIO_CND, d3d9types/D3DSIO_COMMENT, d3d9types/D3DSIO_CRS, d3d9types/D3DSIO_DCL, d3d9types/D3DSIO_DEF, d3d9types/D3DSIO_DEFB, d3d9types/D3DSIO_DEFI, d3d9types/D3DSIO_DP2ADD, d3d9types/D3DSIO_DP3, d3d9types/D3DSIO_DP4, d3d9types/D3DSIO_DST, d3d9types/D3DSIO_DSX, d3d9types/D3DSIO_DSY, d3d9types/D3DSIO_ELSE, d3d9types/D3DSIO_END, d3d9types/D3DSIO_ENDIF, d3d9types/D3DSIO_ENDLOOP, d3d9types/D3DSIO_ENDREP, d3d9types/D3DSIO_EXP, d3d9types/D3DSIO_EXPP, d3d9types/D3DSIO_FORCE_DWORD, d3d9types/D3DSIO_FRC, d3d9types/D3DSIO_IF, d3d9types/D3DSIO_IFC, d3d9types/D3DSIO_LABEL, d3d9types/D3DSIO_LIT, d3d9types/D3DSIO_LOG, d3d9types/D3DSIO_LOGP, d3d9types/D3DSIO_LOOP, d3d9types/D3DSIO_LRP, d3d9types/D3DSIO_M3x2, d3d9types/D3DSIO_M3x3, d3d9types/D3DSIO_M3x4, d3d9types/D3DSIO_M4x3, d3d9types/D3DSIO_M4x4, d3d9types/D3DSIO_MAD, d3d9types/D3DSIO_MAX, d3d9types/D3DSIO_MIN, d3d9types/D3DSIO_MOV, d3d9types/D3DSIO_MOVA, d3d9types/D3DSIO_MUL, d3d9types/D3DSIO_NOP, d3d9types/D3DSIO_NRM, d3d9types/D3DSIO_PHASE, d3d9types/D3DSIO_POW, d3d9types/D3DSIO_RCP, d3d9types/D3DSIO_REP, d3d9types/D3DSIO_RET, d3d9types/D3DSIO_RSQ, d3d9types/D3DSIO_SETP, d3d9types/D3DSIO_SGE, d3d9types/D3DSIO_SGN, d3d9types/D3DSIO_SINCOS, d3d9types/D3DSIO_SLT, d3d9types/D3DSIO_SUB, d3d9types/D3DSIO_TEX, d3d9types/D3DSIO_TEXBEM, d3d9types/D3DSIO_TEXBEML, d3d9types/D3DSIO_TEXCOORD, d3d9types/D3DSIO_TEXDEPTH, d3d9types/D3DSIO_TEXDP3, d3d9types/D3DSIO_TEXDP3TEX, d3d9types/D3DSIO_TEXKILL, d3d9types/D3DSIO_TEXLDD, d3d9types/D3DSIO_TEXLDL, d3d9types/D3DSIO_TEXM3x2DEPTH, d3d9types/D3DSIO_TEXM3x2PAD, d3d9types/D3DSIO_TEXM3x2TEX, d3d9types/D3DSIO_TEXM3x3, d3d9types/D3DSIO_TEXM3x3PAD, d3d9types/D3DSIO_TEXM3x3SPEC, d3d9types/D3DSIO_TEXM3x3TEX, d3d9types/D3DSIO_TEXM3x3VSPEC, d3d9types/D3DSIO_TEXREG2AR, d3d9types/D3DSIO_TEXREG2GB, d3d9types/D3DSIO_TEXREG2RGB, display.shader_operation_codes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d9types.h
req.include-header: 
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
-	d3d9types.h
api_name:
-	D3DSHADER_INSTRUCTION_OPCODE_TYPE
product:
- Windows
targetos: Windows
req.typenames: D3DSHADER_INSTRUCTION_OPCODE_TYPE
---

# _D3DSHADER_INSTRUCTION_OPCODE_TYPE enumeration


## -description


This section lists the operation codes that can be contained in the first 16 bits (0 - 15) of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567721">Instruction Token</a>. The sections that follow describe the token format of the instructions that correspond to the operation codes.


## -enum-fields




### -field D3DSIO_NOP

The NOP instruction performs a no-op, or no operation.


### -field D3DSIO_MOV

The MOV instruction moves data between registers. The instruction length is 2. Can be used for floating-point data and to update address registers. When used to update address registers, the values are converted from floating-point using rounding to nearest.


### -field D3DSIO_ADD

The ADD instruction adds two source vectors and stores the result in the destination.


### -field D3DSIO_SUB

The SUB instruction subtracts two source vectors and stores the result in the destination. Instruction length is 3.


### -field D3DSIO_MAD

The MAD instruction multiplies the first and second sources and adds the third source. Instruction length is 4.


### -field D3DSIO_MUL

The MUL instruction multiplies two source vectors and stores the result in the destination. Instruction length is 3.


### -field D3DSIO_RCP

The RCP instruction computes the reciprocal of the source and stores the result in the destination.

Instruction length is 2. Requires explicit use of replicate swizzle, that is, the X, Y, Z, or W swizzle component (or the R, G, B, or A equivalent) must be specified.


### -field D3DSIO_RSQ

The RSQ instruction computes the reciprocal square root of the source and stores the result in the destination. Instruction length is 2. Requires explicit use of replicate swizzle, that is, the X, Y, Z, or W swizzle component (or the R, G, B, or A equivalent) must be specified.


### -field D3DSIO_DP3

The DP3 instruction computes the three-component (RGB) dot product of the source registers, and stores the result in the destination. Instruction length is 3.


### -field D3DSIO_DP4

The DP4 instruction computes the four-component (RGBA) dot product of the source registers, and stores the result in the destination. Instruction length is 3.


### -field D3DSIO_MIN

The MIN instruction determines the minimum of the sources, and stores the minimum source in the destination.

Instruction length is 3.


### -field D3DSIO_MAX

The MAX instruction determines the maximum of the sources, and stores the maximum source in the destination. Instruction length is 3.


### -field D3DSIO_SLT

The SLT instruction determines whether the first source is less than the second source, and stores the sign (1.0f for TRUE and 0.0f for FALSE) in the destination. Instruction length is 3.


### -field D3DSIO_SGE

The SGE instruction determines whether the first source is greater than or equal to the second source, and stores the sign (1.0f for TRUE and 0.0f for FALSE) in the destination. Instruction length is 3.



### -field D3DSIO_EXP

The EXP instruction provides full precision exponential 2<sup>x</sup>. Instruction length is 2. The source parameter token requires explicit use of replicate swizzle, that is, the X, Y, Z, or W swizzle component (or the R, G, B, or A equivalent) must be specified.
The EXP instruction provides at least 21 bits of precision.




### -field D3DSIO_LOG

The LOG instruction calculates full precision log₂(x). Instruction length is 2.
The source parameter token requires explicit use of replicate swizzle, that is, the X, Y, Z, or W swizzle component (or the R, G, B, or A equivalent) must be specified.
The LOG instruction provides at least 21 bits of precision.


### -field D3DSIO_LIT

The LIT instruction provides partial support for lighting by calculating lighting coefficients from two dot products and an exponent.

Instruction length is 2.
Reduced precision arithmetic is acceptable in evaluating the destination Y component (in write mask). An implementation must support at least eight fraction bits in the power argument. Dot products are calculated with normalized vectors, and clamp limits are -128 to 128. Error should correspond to a LOGP and EXPP combination, or no more than approximately one least significant bit (LSB) for an 8-bit color component.




### -field D3DSIO_DST

The DST instruction calculates a distance vector, and stores the result in the destination. Instruction length is 3.



### -field D3DSIO_LRP

The LRP instruction interpolates linearly between the second and third sources by a proportion specified in the first source, and stores the result in the destination.

Instruction length is 4. The LRP instruction can be used with floating-point data or integer data.

When the LRP instruction is used to update integer registers, the values are converted from floating-point using rounding to the nearest integer.

The LRP instruction must be used to update the address registers.



### -field D3DSIO_FRC

The FRC instruction returns the fractional portion of each input component.

Instruction length is 2.
Each component of the result is in the range from 0.0 through 1.0.

For version vertex or pixel version 1_1, the allowable write masks are Y and XY (X is not allowed).




### -field D3DSIO_M4x4

The M4x4 instruction computes the product of a 4-component vector and a 4x4 matrix, and stores the result in the destination.

Instruction length is 3.
The XYZW mask is required. 
Swizzle components and negate modifiers are invalid. 


### -field D3DSIO_M4x3

TThe M4x3 instruction computes the product of a 4-component vector and a 4x3 matrix, and stores the result in the destination.

Instruction length is 3.
The XYZ mask is required. Swizzle components and negate modifiers are invalid. 



### -field D3DSIO_M3x4

The M3x4 instruction computes the product of a 3-component vector and a 3x4 matrix, and stores the result in the destination.

Instruction length is 3.
The XYZW mask is required. 
Swizzle components and negate modifiers are invalid. 


### -field D3DSIO_M3x3

The M3x3 instruction computes the product of a 3-component vector and a 3x3 matrix, and stores the result in the destination.

Instruction length is 3.
The XYZ mask is required. 
Swizzle components and negate modifiers are invalid.


### -field D3DSIO_M3x2

The M3x2 instruction computes the product of a 3-component vector and a 3x2 matrix, and stores the result in the destination.

Instruction length is 3. The XY mask is required. Swizzle components and negate modifiers are invalid.


### -field D3DSIO_CALL

The CALL instruction performs a function call to the instruction marked with the provided label index. The label token uses the D3DSPR_LABEL register type.


### -field D3DSIO_CALLNZ

The CALLNZ instruction performs a conditional (if not zero) call to the instruction marked by the label index. The label token uses the D3DSPR_LABEL register type. The source parameter token uses the D3DSPR_CONSTBOOL register type.


### -field D3DSIO_LOOP

The LOOP instruction begins a LOOP...ENDLOOP block. Format the second source parameter token using the D3DSPR_CONSTINT register type. The X component specifies the iteration count; the Y component specifies the initial value of the current loop counter register; and the Z component specifies the increment for the current loop counter register. This register requires explicit use of the replicate swizzle, that is, .XYZW (RGBA) component masks must be specified.

Note that only integer registers can be used in the LOOP instruction. The LOOP instruction is provided for iteration, and supports an auto-incremented loop counter register that can be used to index the constant array. When nested, any time the loop counter register is used, it refers to the current loop. 


### -field D3DSIO_RET

The RET instruction returns from a subroutine or marks the end of the main function. If a shader contains no subroutines, using RET at the end of the main program is optional.




### -field D3DSIO_ENDLOOP

The ENDLOOP instruction marks the end of a loop block.


### -field D3DSIO_LABEL

The LABEL instruction marks the next instruction with a label index. Format the source parameter token using the D3DSPR_LABEL register type and a register number.


### -field D3DSIO_DCL

Specifies the <a href="https://msdn.microsoft.com/2833fe6a-f430-4a34-936f-04e997063671">DCL instruction token</a>.


### -field D3DSIO_POW

The POW instruction calculates full precision (src1)<sup>src0</sup>. Instruction length is 3. Both sources require explicit use of replicate swizzle, that is, the X, Y, Z, or W swizzle component (or the R, G, B, or A equivalent) must be specified.

The POW instruction provides at least 15 bits of precision.




### -field D3DSIO_CRS

The CRS instruction computes a cross product using the right-hand rule.




### -field D3DSIO_SGN

The SGN instruction determines the sign of the source and stores the sign (-1 for negative, 0 for 0, and 1 for positive) in the destination. Instruction length is 4. Format the second source parameter token using the D3DSPR_TEMP register type. 

Format the third source parameter token using the D3DSPR_TEMP register type. 

The second and third sources could be used as temporary registers.


### -field D3DSIO_ABS

The ABS instruction computes the absolute value of the source and stores the result in the destination.


### -field D3DSIO_NRM

The NRM instruction normalizes a 4-D vector. Instruction length is 2.



### -field D3DSIO_SINCOS

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff569710">SINCOS instruction</a> computes sine and cosine of the source.


### -field D3DSIO_REP

The REP instruction starts a REPEAT...ENDREP block. Format the source parameter token using the D3DSPR_CONSTINT register type. The X component specifies the iteration count. Only integer registers can be used in the REP instruction. 




### -field D3DSIO_ENDREP

The ENDREP instruction marks the end of a repeat block.


### -field D3DSIO_IF

The IF instruction begins an IF block. Format the source parameter token using the D3DSPR_CONSTBOOL register type. If the source Boolean register is TRUE, the code enclosed by the IF statement and the matching ELSE (or ENDIF if ELSE is not used) is executed; otherwise the execution passes to the code enclosed by the ELSE-ENDIF statements (ELSE exists) or out of the IF block (ELSE does not exist). 


### -field D3DSIO_IFC

The IFC instruction begins an IF block with a comparison. The IFC instruction skips a block of code, based on the comparison between sources.

Both sources require explicit use of replicate swizzle, that is, the X, Y, Z, or W swizzle component (or the R, G, B, or A equivalent) must be specified.

If the comparison between all source components is TRUE, the code enclosed by the IF statement and the matching ELSE instruction (or ENDIF instruction if ELSE is not used) is executed; otherwise the execution passes to the code enclosed by the ELSE-ENDIF statements (ELSE exists) or out of the IF block (ELSE does not exist).



### -field D3DSIO_ELSE

The ELSE instruction starts an ELSE block. If the source Boolean register in the corresponding IF instruction is true, the code that is enclosed by the IF and the matching ELSE is executed, otherwise execution passes to the code that is enclosed by the ELSE and the ENDIF instructions.




### -field D3DSIO_ENDIF

The ENDIF instruction ends an IF...ELSE block.


### -field D3DSIO_BREAK

The BREAK instruction breaks out of the current loop at the nearest endloop or endrep.


### -field D3DSIO_BREAKC

The BREAK_COMP instruction breaks out of the current loop at the nearest endloop or endrep, based on the comparison criteria between two sources.


### -field D3DSIO_MOVA

The MOVA instruction moves data from floating-point register to integer register. Instruction length is 2. The values are converted from floating-point using rounding to nearest.

The address register is the only destination register allowed.




### -field D3DSIO_DEFB

The DEFB instruction defines a Boolean constant value, which should be loaded anytime a shader is set to a device. This instruction can be used in vertex shader 2_0 and later versions. Boolean constants that are set by the current vertex shader take precedence over constants that are set by the D3DDP2OP_SETVERTEXSHADERCONSTB operation.

Instruction length is 2.
The register type must be D3DSPR_CONSTBOOL. The format of the DWORD token contains the Boolean value, where nonzero indicates TRUE; zero indicates FALSE.


### -field D3DSIO_DEFI

The DEFI instruction defines an integer constant value, which should be loaded anytime a shader is set to a device. Constants that are set by the current vertex shader take precedence over constants that are set by the D3DDP2OP_SETVERTEXSHADERCONSTI operation.

Instruction length is 5.
The register type must be D3DSPR_CONSTINT. The format of the 4 DWORD tokens contains four 32-bit signed integers.




### -field D3DSIO_TEXCOORD

The TEXCOORD instruction copies texture coordinate data (UVW1) as color data (RGBA). 

<div class="alert"><b>Note</b>  The source parameter token is for pixel shader version 1_4 only.

The texcoord and texcrd assembler instructions both use the D3DSIO_TEXCOORD operation code. 

The texcoord instruction applies to pixel shader versions 1_0 through 1_3; it has one destination parameter token and no source parameter token associated with it. 

The texcrd instruction applies to pixel shader version 1_4; it has one destination parameter token and one source parameter token associated with it. 
</div>
<div> </div>

### -field D3DSIO_TEXKILL

The TEXKILL instruction cancels rendering of the current pixel if any of the first three components (UVW) of the texture coordinates is less than zero.

If any of the components of the destination token is less than zero, terminate the pixel shader and discard the outputs.

The following features apply to the destination token:

<ul>
<li>A temporary (D3DSPR_TEMP) or texture (D3DSPR_TEXTURE) register type must be used.</li>
<li>If a temporary register is used, all components must have been previously written.</li>
<li>If a texture register is used, all components that are read must have been declared.</li>
<li>A complete write mask must be specified.</li>
</ul>

### -field D3DSIO_TEX

The TEX instruction loads destination with color data (RGBA) that is sampled from the source texture. Format the destination parameter token using the D3DSPR_PREDICATE register type. The following source tokens are for pixel shader version 1_4 and later only: the first source parameter token provides the texture coordinates for the texture sample, and the

second source parameter token using the D3DSPR_SAMPLER register type. The second source parameter token identifies the texture sampler number to sample. 



<div class="alert"><b>Note</b>  The tex and texld assembler instructions both use the D3DSIO_TEX operation code. 

The tex instruction applies to pixel shader versions 1_0 through 1_3; it has one destination parameter token and no source parameter tokens associated with it. 

The texld instruction applies to pixel shader version 1_4 and later; it has one destination parameter token and two source parameter tokens associated with it.</div>
<div> </div>

### -field D3DSIO_TEXBEM

The TEXBEM instruction applies a bump environment-map transform by modifying the texture address data of the destination register, using address perturbation data (U,V), and a 2-D bump environment matrix. 


### -field D3DSIO_TEXBEML

The TEXBEML instruction applies a bump environment-map transform with luminance correction. The bump environment-map transform with luminance correction is accomplished by modifying the texture address data of the destination register, using address perturbation data (U.V), a 2-D bump environment matrix, and luminance.


### -field D3DSIO_TEXREG2AR

The TEXREG2AR instruction interprets the alpha and red color components of the source as texture address data (U,V) in order to sample the texture at the stage corresponding to the destination register number. The result is stored in the destination.

The TEXREG2AR instruction is useful for color-space remapping operations. It supports two-dimensional (2-D) coordinates. 

The source register must use unsigned data; if the source register uses signed or mixed data, the operation produces invalid results.




### -field D3DSIO_TEXREG2GB

The TEXREG2GB instruction interprets the green and blue color components of the source as texture address data (U,V) in order to sample the texture at the stage corresponding to the destination register number. The result is stored in the destination. The TEXREG2GB instruction is useful for color-space remapping operations. It supports two-dimensional (2-D) coordinates. 

The source register must use unsigned data; if the source register uses signed or mixed data, the operation produces invalid results.




### -field D3DSIO_TEXM3x2PAD

The TEXM3x2PAD instruction performs the first row multiplication of a two-row matrix multiply. The TEXM3x2PAD instruction cannot be used by itself; it must be combined with either the TEXM3x2TEX or TEXM3x2DEPTH instructions.


### -field D3DSIO_TEXM3x2TEX

The TEXM3x2TEX instruction performs the final row of a 3x2 matrix multiply and uses the result in a texture lookup. The TEXM3x2TEX instruction must be used with the TEXM3x2PAD instruction.


### -field D3DSIO_TEXM3x3PAD

The TEXM3x3PAD instruction performs the first or second row multiply of a three-row matrix multiply. The TEXM3x3PAD instruction cannot be used by itself; it must be combined with the TEXM3x3 instruction, TEXM3x3SPEC instruction, TEXM3x3VSPEC instruction, or TEXM3x3TEX instruction.




### -field D3DSIO_TEXM3x3TEX

The TEXM3x3TEX instruction performs a 3x3 matrix multiply and uses the result in a texture lookup. The TEXM3x3TEX instruction must be used with two TEXM3x3PAD instructions. 

It is used as the final of three instructions representing a 3x3 matrix multiply operation, followed by a texture lookup. The 3x3 matrix is comprised of the texture coordinates of the third texture stage and the two preceding texture stages. The resulting three-component vector (U,V,W) is used to sample the texture in stage 3. Any texture assigned to the preceding two texture stages is ignored. The 3x3 matrix multiply is typically useful for orienting a normal vector to the correct tangent space for the surface being rendered.




### -field D3DSIO_RESERVED0


### -field D3DSIO_TEXM3x3SPEC

The TEXM3x3SPEC instruction performs a 3x3 matrix multiply and uses the result in a texture lookup. Used for specular reflection and environment mapping. The TEXM3x3SPEC instruction must be used with two TEXM3x3PAD instruction. This instruction set can be used for specular reflection and environment mapping.

The TEXM3x3SPEC instruction performs the final row of a 3x3 matrix multiply, uses the resulting vector as a normal vector to reflect an eye-ray vector, and then uses the reflected vector to perform a texture lookup. The shader reads the eye-ray vector from a constant register. The 3x3 matrix multiply is typically useful for orienting a normal vector to the correct tangent space for the surface being rendered.

The 3x3 matrix is comprised of the texture coordinates of the third texture stage and the two preceding texture stages. The resulting post reflection vector (U,V,W) is used to sample the texture on the final texture stage. Any texture assigned to the preceding two texture stages is ignored.




### -field D3DSIO_TEXM3x3VSPEC

The TEXM3x3VSPEC instruction performs a 3x3 matrix multiply and uses the result in a texture lookup. Used for specular reflection and environment mapping where the eye-ray vector is not constant. The TEXM3x3VSPEC instruction must be used with two TEXM3x3PAD instructions. This instruction set can be used for specular reflection and environment mapping where the eye-ray vector is not constant. If the eye-ray vector is constant, the TEXM3x3SPEC instruction performs the same matrix multiply and texture lookup.

The TEXM3x3VSPEC instruction performs the final row of a 3x3 matrix multiply operation, interprets the resulting vector as a normal vector to reflect an eye-ray vector, and then uses the reflected vector as a texture address for a texture lookup. It works just like TEXM3X3SPEC, except that the eye-ray vector is taken from the fourth component of the texture coordinates. The 3x3 matrix multiply is typically useful for orienting a normal vector to the correct tangent space for the surface being rendered.

The 3x3 matrix is comprised of the texture coordinates of the third texture stage and the two preceding texture stages. The resulting postreflection vector (UVW) is used to sample the texture in stage 3. Any texture assigned to the preceding two texture stages is ignored.




### -field D3DSIO_EXPP

The EXPP instruction provides partial precision exponential 2<sup>x</sup>. Instruction length is 2.
The source parameter token requires explicit use of replicate swizzle, that is, the X, Y, Z, or W swizzle component (or the R, G, B, or A equivalent) must be specified.
The EXPP instruction provides at least 10 bits of precision.




### -field D3DSIO_LOGP

The LOGP instruction calculates partial precision log₂(x). Instruction length is 2. The source parameter token requires explicit use of replicate swizzle, that is, the X, Y, Z, or W swizzle component (or the R, G, B, or A equivalent) must be specified.
The LOGP instruction provides at least 10 bits of precision.


### -field D3DSIO_CND

The CND instruction chooses between the second and third sources, based on the first source being greater than 0.5, and stores the result in the destination.


### -field D3DSIO_DEF

The DEF instruction defines a constant value, which should be loaded anytime a shader is set to a device. This instruction can be used in all vertex shader versions. Constants that are set by the current vertex shader take precedence over constants that are set by the D3DDP2OP_SETVERTEXSHADERCONST operation.

Instruction length is 5. The register type must be D3DSPR_CONST, D3DSPR_CONST2, D3DSPR_CONST3, or D3DSPR_CONST4. The format of the 4 DWORD tokens is a 4-D floating-point number or 4-D integer number.




### -field D3DSIO_TEXREG2RGB

The TEXREG2RGB instruction interprets the red, green, and blue (RGB) color components of the source as texture address data (U,V,W) in order to sample the texture at the stages corresponding to the destination register number. The result is stored in the destination.

The TEXREG2RGB instruction is useful for color-space remapping operations. It supports two-dimensional (2-D) and three-dimensional (3-D) coordinates. It can be used just like the TEXREG2AR instruction or TEXREG2GB instruction to remap 2-D data. However, the TEXREG2RGB instruction also supports 3-D data so it can be used with cube maps and 3-D volume textures.




### -field D3DSIO_TEXDP3TEX

The TEXDP3TEX instruction performs three-component dot product and uses the result to do a 1-D texture lookup.


### -field D3DSIO_TEXM3x2DEPTH

The TEXM3x2DEPTH instruction calculates the depth value to be used in depth testing for a pixel.

The TEXM3x2DEPTH instruction must be used with the TEXM3x2PAD instruction.




### -field D3DSIO_TEXDP3

The TEXDP3 instruction performs a three-component dot product between data in the texture register number and the texture coordinate set corresponding to the destination register number.


### -field D3DSIO_TEXM3x3

The TEXM3x3 instruction performs 3x3 matrix multiply when used in conjunction with two TEXM3x3PAD instructions.




### -field D3DSIO_TEXDEPTH

The TEXDEPTH instruction calculates depth value to be used in pixel depth buffer comparison test.


### -field D3DSIO_CMP

The CMP instruction chooses between the second and third sources, based on the first source being greater than or equal to zero, and stores the result in the destination. The comparison is done per channel.




### -field D3DSIO_BEM

The BEM instruction applies a bump environment-map transform.


### -field D3DSIO_DP2ADD

The DP2ADD instruction performs a 2-D dot product and scalar addition, and stores the result in the destination. 

Instruction length is 4.



### -field D3DSIO_DSX

The DSX instruction computes the rate of change of the source in the x direction, and stores the result in the destination. The DSX instruction always computes gradients on the current contents of registers in pixels, regardless of whether the pixels are active either due to flow control or due to being off the edge of a primitive. These pixels are executed in lockstep. Instruction length is 2. The destination parameter token accepts all write masks. The source parameter token accepts all swizzles. 


### -field D3DSIO_DSY

The DSY instruction computes the rate of change of the source in the y direction, and stores the result in the destination. 

Instruction length is 2.
The DSY instruction always computes gradients on the current contents of registers in pixels, regardless of whether the pixels are active either due to flow control or due to being off the edge of a primitive. These pixels are executed in lockstep. The destination parameter token accepts all write masks. The source parameter token accepts all swizzles.


### -field D3DSIO_TEXLDD

The TEXLDD instruction samples a texture using the texture coordinates in the first source token, the sampler specified by the second source token, and the gradients (DSX and DSY) from the third and fourth source tokens. Instruction length is 5. Format a second source parameter token that must use the D3DSPR_SAMPLER register type. The sampler states that are supported are D3DSAMP_MAXMIPLEVEL and D3DSAMP_MIPMAPLODBIAS.



<div class="alert"><b>Note</b>  All sources support arbitrary swizzles. 

All write masks are valid on the destination. 
</div>
<div> </div>

### -field D3DSIO_SETP

The SETP instruction sets the predicate register. Instruction length is 3.
Format the destination parameter token using the D3DSPR_PREDICATE register type. It requires write masks.

For the first and second source parameter tokens, swizzle components must be specified.
For each channel that can be written according to the destination write mask, save the Boolean result of the comparison operation between the corresponding channels of the sources (after the source modifier swizzles are resolved). 


### -field D3DSIO_TEXLDL

The TEXLDL instruction samples a texture at a particular sampler using the provided texture coordinates. The particular level of detail (LOD) that is sampled must be specified as the fourth (W) component of the texture coordinate. Instruction length is 3. Format the destination parameter token using the D3DSPR_PREDICATE register type. 

The first source parameter token must provide the texture coordinates for the texture sample.

Format the second source parameter token using the D3DSPR_SAMPLER register type. It identifies the texture sampler number to sample. The Negate source modifier cannot be specified. Swizzle can be specified. The sampler number must be declared at the beginning of the shader.


<div class="alert"><b>Note</b>  <ul>
<li>The default values for missing components of the destination token's write mask are either 0 or 1, and depend on the texture format.</li>
<li>The number of coordinates that are required to perform the texture sample depends on how the sampler number was declared. If it was declared as a cube, a 3-component texture coordinate (RGB) is required. Validation enforces that coordinates that are provided to texld are sufficient for the texture dimension that is declared for the sampler. Sampling a texture with lower dimensions than are present in the texture coordinate is valid. Conversely, sampling a texture with higher dimensions than are present in the texture coordinate is invalid.</li>
<li>Sampling unsigned RGB textures results in float values that are from 0.0 to 1.0. </li>
<li>Sampling signed textures results in float values that are from -1.0 to 1.0.</li>
<li>Sampling floating-point textures results in the Float16 to MAX_FLOAT16 range being preserved, or 

the Float32 to Max range of pipeline being preserved. 
</li>
</ul>
</div>
<div> </div>

### -field D3DSIO_BREAKP

The BREAK PRED instruction breaks out of the current loop at the nearest endloop or endrep by using one of the components of the predicate register as a condition to determine whether to perform the instruction. Format the source parameter token using the D3DSPR_PREDICATE register type with a replicate swizzle (each channel uses the same source component). The NOT (0xd) source modifier in bits 27:24 is permitted.


### -field D3DSIO_PHASE

The PHASE instruction marks the transition between pixel shader version 1 and 2. If no phase instruction is present, the entire shader runs as if it is a phase 2 shader.

Note that this value applies to Pixel shader version 1_4 only. Shader instructions that occur before the PHASE instruction are phase 1 instructions. All other instructions are phase 2 instructions. By having two phases for instructions, the maximum number of instructions per shader is increased.

The alpha component of temporary registers do not persist across the phase transition. In other words, the alpha component must be reinitialized after the phase instruction.




### -field D3DSIO_COMMENT

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539503">comment token</a>.


### -field D3DSIO_END

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564170">end token</a>.


### -field D3DSIO_FORCE_DWORD

Forces a 32 bit size.

