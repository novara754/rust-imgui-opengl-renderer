# imgui-opengl-renderer

> This is a fork of [michaelfairley/rust-imgui-opengl-renderer](https://github.com/michaelfairley/rust-imgui-opengl-renderer)
> the uses the latest version of imgui straight from GitHub.

OpenGL (3+) rendering for [imgui-rs](https://github.com/Gekkio/imgui-rs)

## Integration guide

1. Construct it (passing in an OpenGL function loader from [SDL2](https://github.com/Rust-SDL2/rust-sdl2) or [glutin](https://github.com/tomaka/glutin) or somesuch).
   ```rust
   let renderer = imgui_opengl_renderer::Renderer::new(&mut imgui, |s| video.gl_get_proc_address(s) as _);
   ```
2. Call `render` to draw the UI.
   ```rust
   renderer.render(ui);
   ```

Take a look at the [example app](./examples/demo.rs) to see it all in context.
