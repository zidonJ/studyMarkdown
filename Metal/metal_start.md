---
title: metal_start
date: 2021-10-09 15:10
---

### 协议
- id<MTLDevice> _device;
- id<MTLRenderPipelineState> _pipelineState;
>  The render pipeline generated from the vertex and fragment shaders in the .metal shader file.
- id<MTLCommandQueue> _commandQueue;
> The command queue used to pass commands to the device.
- vector_uint2 _viewportSize;
> The current size of the view, used as an input to the vertex shader.

- id<MTLLibrary> defaultLibrary = [_device newDefaultLibrary];
>  Load all the shader files with a .metal file extension in the project.
- id<MTLFunction> vertexFunction = [defaultLibrary newFunctionWithName:@"vertexShader"];
>  顶点着色
- id<MTLFunction> fragmentFunction = [defaultLibrary newFunctionWithName:@"fragmentShader"];
>  片段着色

- _pipelineState = [_device newRenderPipelineStateWithDescriptor:pipelineStateDescriptor error:&error];
>  创建渲染管线 有可能失败

- _commandQueue = [_device newCommandQueue];
>  Create the command queue
