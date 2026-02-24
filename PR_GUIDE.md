# Pull Request 准备指南

## PR标题
feat: Add Deep Search and Deep Research support

## PR描述

### 新增功能

本PR为UniFuncs MCP服务器添加了深度搜索和深度研究功能的完整支持。

#### 新增工具

1. **deep-search-sync** - 深度搜索同步接口
   - 实时返回深度搜索结果
   - 支持流式输出

2. **deep-search-create-task** - 深度搜索异步创建任务
   - 立即返回task_id
   - 后台执行搜索任务

3. **deep-search-query-task** - 深度搜索查询任务
   - 查询任务状态和进度
   - 获取完成的搜索结果

4. **deep-research-create-task** - 深度研究创建任务
   - 可定制研究参数：
     - 研究员角色设定
     - 引用格式（link/number/footnote）
     - 最大研究深度（1-50轮）
     - 域名范围限制
     - 域名黑名单
     - 自定义输出提示词
     - 重点URL和关键词

5. **deep-research-query-task** - 深度研究查询任务
   - 查询研究进度
   - 获取研究结果

### 改进

- 版本升级到0.1.0
- 完善的README文档
- 详细的工具使用示例
- Zod参数验证

### 技术细节

- 保持与现有代码风格一致
- 使用相同的request辅助函数
- 完整的错误处理
- TypeScript类型安全

### 测试

已通过实际API调用测试：
- ✅ 深度搜索创建任务
- ✅ 深度搜索查询任务
- ✅ API响应格式正确
- ✅ 错误处理正常

### Breaking Changes

无。所有现有功能保持向后兼容。

## 提交步骤

### 1. Fork仓库
```bash
# 在GitHub上fork
https://github.com/UniFuncs/ufn-mcp-server
```

### 2. 克隆你的fork
```bash
git clone https://github.com/YOUR_USERNAME/ufn-mcp-server.git
cd ufn-mcp-server
```

### 3. 创建feature分支
```bash
git checkout -b feature/add-deep-search-research
```

### 4. 复制增强版文件
```bash
cp /tmp/ufn-mcp-server-enhanced/index.ts .
cp /tmp/ufn-mcp-server-enhanced/package.json .
cp /tmp/ufn-mcp-server-enhanced/README.md .
```

### 5. 提交更改
```bash
git add index.ts package.json README.md
git commit -m "feat: Add Deep Search and Deep Research support

- Add deep-search-sync tool for real-time deep search
- Add deep-search-create-task and query-task for async deep search
- Add deep-research-create-task and query-task for comprehensive research
- Update version to 0.1.0
- Enhance README with complete tool documentation
- Add examples for all new tools"
```

### 6. 推送到fork
```bash
git push origin feature/add-deep-search-research
```

### 7. 创建Pull Request
- 访问 https://github.com/YOUR_USERNAME/ufn-mcp-server
- 点击 "Compare & pull request"
- 填写标题和描述
- 提交PR

## 注意事项

1. **API Key安全**: 不要在代码中包含你的API Key
2. **测试覆盖**: 如可能，添加单元测试
3. **文档完整**: 确保所有新功能都有文档说明
4. **向后兼容**: 不破坏现有功能

## 预期结果

PR合并后，UniFuncs MCP服务器将支持：

- ✅ 实时网页搜索（web-search）
- ✅ 网页内容抓取（web-reader）
- ✅ 深度搜索 - 同步模式
- ✅ 深度搜索 - 异步模式（create + query）
- ✅ 深度研究 - 异步模式（create + query）

这将为所有MCP用户提供完整的UniFuncs API能力。
