# 离线记事本 (Offline Notepad)

这是一个简洁的离线记事本网页应用，文件名为 `notepad.html`。它旨在在浏览器中提供基本的文本编辑、打开与保存功能，并在支持的浏览器上使用 File System Access API 以实现更好的本地读写体验。

**功能**
- 新建、打开、保存、另存为文本文件（.txt）
- 自动统计字符数与行数
- 键盘快捷键：
  - `Ctrl/Cmd + S`：保存
  - `Ctrl/Cmd + O`：打开
  - `Ctrl/Cmd + N`：新建
- 支持 File System Access API（打开/保存为原地读写）
- 不支持该 API 时降级为文件输入打开和下载保存

**使用方法**
1. 在浏览器中打开 `notepad.html`（双击或通过本地服务器）。
2. 在编辑区输入文本；顶部工具栏提供“新建/打开/保存/另存为/清空”等操作按钮。
3. 若浏览器支持 File System Access API（例如 Chromium 系列的现代版本），打开与保存会尽可能在用户选择的本地路径上直接读写；否则会使用经典的文件选择对话或触发下载保存文件到默认下载目录。
4. 可在“默认文件名”输入框中设置另存为时的建议文件名。

**兼容性与注意事项**
- 推荐使用基于 Chromium 的浏览器（如 Chrome、Edge）以获得最佳原生保存/打开体验。
- Safari / Firefox 等部分浏览器可能不支持 `showOpenFilePicker` / `showSaveFilePicker`，此时会回退到 `<input type="file">` 打开或通过生成下载文件保存。
- 页面在有未保存更改时会阻止关闭/刷新，防止数据丢失。
