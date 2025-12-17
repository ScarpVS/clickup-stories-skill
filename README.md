# ClickUp Stories Skill

A Claude skill for creating structured frontend development stories in ClickUp using a standardized template for connected vehicle products.

## Overview

This skill provides an interactive workflow for creating comprehensive user stories with all necessary context for frontend development teams working on connected vehicle products. It ensures consistent story structure across the team and includes all mandatory sections required for effective planning, development, and QA.

## Features

### **Interactive Story Creation**
- Guided information gathering for all story components
- Systematic template completion with validation
- Support for mandatory and optional sections
- Intelligent handling of missing information with placeholders

### **Connected Vehicle Domain Expertise**
- Vehicle-specific context (Base, Connected, AVK, EV, AVK2, AVK2EV, EVO)
- Frontend development focus with UX/UI considerations
- Blast radius assessment for regression risk management
- Requirements gathering tailored to automotive products

### **Template Preservation**
- Complete template structure always maintained
- Emoji headers and table formatting preserved
- Markdown structure consistency enforced
- "[TBD]" placeholders for incomplete information

## Template Structure

The skill generates stories with these sections:

### **Mandatory Sections**
- ⏱️ **Timing** - Target dates and dependencies
- 📖 **Context** - What we're building and why
- 🎯 **Scope & Requirements** - Vehicle types, capabilities, access levels
- 💥 **Blast Radius** - Impact assessment and regression risks
- ✅ **Acceptance Criteria** - Given/When/Then scenarios
- ✅ **Done When** - Completion checklist

### **Optional Sections** (included when applicable)
- 🚧 **Blockers** - Dependencies and obstacles
- 🏁 **Feature Flags** - Flag configurations
- ⚙️ **Technical Specifications** - Cache strategy, architecture
- 🎨 **Design Specifications** - Figma links, localization
- 💾 **Data Requirements** - GraphQL queries/mutations
- 📊 **Analytics Tracking** - Event tracking requirements
- 🧪 **QA Notes** - Test accounts and observations

## Prerequisites

### **ClickUp MCP Server**
This skill requires the [ClickUp MCP Server](https://github.com/ScarpVS/clickup-mcp-server) to function. The MCP server provides the API integration for creating tasks in ClickUp.

Install the MCP server:
```bash
pip install clickup-mcp-server
```

Configure in Claude Desktop:
```json
{
  "mcpServers": {
    "clickup-stories-mcp": {
      "command": "python",
      "args": ["-m", "clickup_mcp.server"],
      "env": {
        "CLICKUP_API_TOKEN": "your_token_here",
        "CLICKUP_TEAM_ID": "your_team_id",
        "CLICKUP_DEFAULT_LIST_ID": "your_list_id"
      }
    }
  }
}
```

### **ClickUp Configuration**
The skill is configured for:
- **Target List**: NMEX Project Tracker (`901406617827`)
- **Default Assignee**: Vitor Scarpinetti (`96271408`)
- **Default Status**: `icebox`
- **Platform Field**: Custom dropdown field for iOS/Android/Web/Backend
- **Tags**: `["frontend", "connected-vehicle", "story"]`

## Installation

1. **Download the skill file**:
   ```bash
   curl -o SKILL.md https://raw.githubusercontent.com/ScarpVS/clickup-stories-skill/main/SKILL.md
   ```

2. **Place in Claude Skills directory**:
   ```
   ~/Documents/Claude Skills/clickup-stories/SKILL.md
   ```

3. **Ensure MCP server is configured** (see prerequisites above)

## Usage

### **Basic Story Creation**
1. Tell Claude: "Create a new ClickUp story"
2. Follow the interactive prompts
3. Provide information for each section
4. Claude will create the story with complete template

### **Advanced Usage**
- Specify vehicle types and capabilities
- Define blast radius with regression risk assessment
- Include technical specifications for complex features
- Add design requirements with Figma links
- Configure feature flags and analytics tracking

### **Example Interaction**
```
User: "Create a story for implementing a vehicle battery status widget"

Claude: "I'll help you create a story using your team's comprehensive template. Let's gather all the information systematically.

What's the story title?"

User: "iOS: Vehicle Battery Status Widget"

Claude: "What are we building and why? What are the key requirements/use cases?"

[... interactive flow continues ...]
```

## Vehicle Types Reference

- **Base Vehicle** - Standard vehicle without connectivity
- **Connected** - Vehicle with connected services
- **AVK** - Advanced Vehicle Kit
- **EV** - Electric Vehicle
- **AVK2** - Advanced Vehicle Kit 2nd generation
- **AVK2EV** - Advanced Vehicle Kit 2 Electric Vehicle
- **EVO** - Evolution platform

## Regression Risk Guidelines

- 🔴 **High** - Core functionality, shared services, multiple touchpoints
- 🟡 **Medium** - Feature-specific with some shared components
- 🟢 **Low** - Isolated change, minimal dependencies

## Best Practices

### **Information Gathering**
- Always collect all mandatory sections before creating
- Ask clarifying questions about vehicle types and capabilities
- Help assess blast radius and regression risks
- Use Given/When/Then format for acceptance criteria

### **Template Integrity**
- Never abbreviate or skip sections
- Preserve emoji headers and table formatting
- Use "[TBD]" for missing information rather than omitting
- Maintain consistent section ordering

### **Story Quality**
- Focus on frontend development context
- Include UX/UI considerations when applicable
- Consider cross-platform implications (iOS/Android/Web)
- Assess impact on shared components and services

## Customization

### **Adapting for Your Team**
To customize this skill for your organization:

1. **Update ClickUp Configuration**:
   - Change `list_id` to your target list
   - Update `assignees` default
   - Modify custom field IDs and options

2. **Modify Template Sections**:
   - Add/remove optional sections as needed
   - Customize vehicle types for your product
   - Adjust acceptance criteria format

3. **Update Domain Context**:
   - Replace connected vehicle context with your domain
   - Modify technical specifications sections
   - Adapt blast radius categories

## Troubleshooting

### **Common Issues**

**Skill not responding**:
- Verify SKILL.md is in correct Claude Skills directory
- Check MCP server configuration in Claude Desktop

**Missing template sections**:
- Ensure you're using the complete SKILL.md file
- Verify all mandatory sections are present in the template

**ClickUp creation errors**:
- Check MCP server logs for authentication issues
- Verify list permissions and custom field access
- Confirm user ID mapping for assignees

### **Validation**
Use this checklist to verify stories are created correctly:

- [ ] All mandatory sections present (⏱️ 📖 🎯 💥 ✅ ✅)
- [ ] Emoji headers preserved
- [ ] Table formatting maintained
- [ ] No abbreviated or summarized sections
- [ ] Given/When/Then format for acceptance criteria
- [ ] Proper assignee and custom field mapping

## Contributing

1. Fork the repository
2. Create a feature branch
3. Test changes with actual story creation
4. Update documentation as needed
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For issues and questions:
- Review the troubleshooting section
- Check the [ClickUp MCP Server](https://github.com/ScarpVS/clickup-mcp-server) for API integration issues
- Open an issue on GitHub with story creation examples

---

**Connected Vehicle Story Template for Frontend Development Teams**