# imgui-java

一个基于Android平台的ImGui Java绑定项目，允许开发者在Android应用中使用Dear ImGui库创建交互式用户界面。

## 项目功能

- ✅ 集成Dear ImGui库到Android应用
- ✅ 支持基本ImGui控件（按钮、滑块、颜色选择器等）
- ✅ 支持中文输入和显示
- ✅ 实现触摸事件处理
- ✅ 提供JNI接口，实现Java和C++之间的通信
- ✅ 示例窗口展示

## 项目结构

```
imgui-java/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── cpp/             # C++代码
│   │   │   │   ├── imgui/       # ImGui库源码
│   │   │   │   ├── xdl/         # 用于获取JavaVM的库
│   │   │   │   ├── Incluedes/   # 头文件
│   │   │   │   ├── JniInterface/# JNI接口
│   │   │   │   ├── ImGuiWrapper.cpp  # JNI接口实现
│   │   │   │   └── CMakeLists.txt
│   │   │   ├── java/            # Java代码
│   │   │   │   └── com/xa/JavaImgui/  # 主包
│   │   │   ├── res/             # 资源文件
│   │   │   └── libs/            # 编译后的库文件
│   │   └── build.gradle
│   └── build.gradle
├── gradle/
└── build.gradle
```

## 核心文件

- **MainActivity.java**：主Activity，加载本地库
- **ImGuiWrapper.cpp**：JNI接口实现，处理ImGui初始化、渲染和事件
- **imgui/**：ImGui库源码，包含核心功能实现

## 技术实现

1. **JNI接口**：通过JNI实现Java和C++之间的通信
2. **OpenGL ES**：使用OpenGL ES进行渲染
3. **ImGui**：集成Dear ImGui库，提供UI控件
4. **触摸事件**：实现触摸事件的处理和传递
5. **中文支持**：添加中文字体支持


## 构建和运行

1. 推荐使用Android Studio打开项目
2. 同步Gradle依赖
3. 构建并运行应用
4. 应用启动后，会显示ImGui示例窗口

## 注意事项

- 项目使用CMake构建C++代码
- 项目使用xdl库获取反射调用
- java部分代码实际只用于加载本地库，不包含ImGui的渲染逻辑
- 支持的架构：arm64-v8a、armeabi-v7a、x86、x86_64
- 已包含预编译的库文件在libs目录

## 扩展和定制

- 可以通过修改`renderDemoWindow()`函数添加自定义UI
- 可以通过JNI接口添加更多功能
- 可以根据需要调整ImGui的样式和配置

## 许可证

本项目基于Dear ImGui库，遵循其许可证条款。

## 致谢

- [Dear ImGui](https://github.com/ocornut/imgui) - 一个即时模式的图形用户界面库
- [xdl](https://github.com/hexhacking/xDL) - 用于获取JavaVM的库

---

**imgui-java** - 让Android应用开发更加直观和高效！
