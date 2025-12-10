# Best Practices

> Tips and recommendations for maximizing the effectiveness of the AI-Assisted Development Framework

---

## 🎯 General Principles

### 1. Maintain Control

You are the pilot; AI agents are your co-pilots.

- **Review every output** - Never blindly accept AI-generated content
- **Understand the code** - If you can't explain it, don't ship it
- **Make final decisions** - AI suggests, you decide
- **Stay accountable** - You own the final product

### 2. Context is King

The quality of AI output directly correlates with context quality.

- **Run `/init` at every session start** - Fresh context prevents drift
- **Use `/clear` between tasks** - Focused context yields focused output
- **Write detailed user stories** - More detail = better PRDs
- **Maintain ADRs actively** - They're the AI's rulebook

### 3. Embrace Iteration

Perfection is achieved through refinement, not first attempts.

- **Review PRDs thoroughly** before task decomposition
- **Refine task definitions** before implementation
- **Address review feedback** before moving on
- **Update ADRs** when you learn better patterns

---

## 📝 Planning Best Practices

### Writing Effective User Stories

**Do:**
```
As a registered user who has forgotten my password,
I want to receive a password reset email with a secure link,
So that I can regain access to my account without contacting support.

Acceptance Criteria:
- Reset request available from login page
- Email sent within 30 seconds
- Link expires after 24 hours
- Password must meet current security policy
- Account is locked after 3 failed reset attempts
```

**Don't:**
```
User needs password reset feature.
```

### PRD Quality Checks

Before approving a PRD, verify:

- [ ] All user stories have clear acceptance criteria
- [ ] Non-functional requirements include measurable targets
- [ ] Security considerations match the risk level
- [ ] ADR references are accurate and complete
- [ ] Out of scope is explicitly defined
- [ ] Dependencies are identified and addressed

---

## 📊 Task Decomposition Best Practices

### Optimal Task Size

| Size | Hours | Characteristics |
|------|-------|-----------------|
| S | 1-2 | Single file, single concept |
| M | 2-4 | Few files, clear scope ⭐ Sweet spot |
| L | 4-8 | Multiple files, one feature |
| XL | 8+ | Break it down further! |

### Task Independence

Strive for tasks that can be:
- **Implemented independently** (minimize blockers)
- **Tested independently** (unit testable)
- **Reviewed independently** (small, focused PRs)
- **Deployed independently** (feature flags if needed)

### Dependency Management

```
Good:
TASK-001 (Foundation) → TASK-002 (Core) → TASK-003 (Features)

Bad:
TASK-001 ←→ TASK-002 ←→ TASK-003  (Circular!)
```

---

## 💻 Development Best Practices

### Choosing Specialization

| Scenario | Specialization | Why |
|----------|----------------|-----|
| API endpoint | `backend` | Server focus |
| React component | `frontend` | UI focus |
| Full feature with API + UI | `fullstack` | End-to-end |
| Database migration | `backend` | Data layer |
| Form validation | `frontend` | Client logic |

### Code Quality Reminders

Before marking a task complete:

- [ ] No `console.log` statements left
- [ ] No `any` types without comments
- [ ] No commented-out code
- [ ] All functions have documentation
- [ ] Edge cases are handled
- [ ] Error handling is comprehensive
- [ ] Tests are meaningful (not just for coverage)

### Testing Strategy

```typescript
// ✅ Good: Tests behavior
describe('PasswordResetService', () => {
  it('should send reset email when user exists', async () => {
    // Arrange
    const user = createTestUser();
    // Act
    await service.requestReset(user.email);
    // Assert
    expect(emailService.send).toHaveBeenCalledWith(
      expect.objectContaining({ to: user.email })
    );
  });

  it('should throw when rate limit exceeded', async () => {
    // Arrange
    await service.requestReset(email);
    await service.requestReset(email);
    await service.requestReset(email);
    // Act & Assert
    await expect(service.requestReset(email))
      .rejects.toThrow(RateLimitError);
  });
});

// ❌ Bad: Tests implementation
describe('PasswordResetService', () => {
  it('should call generateToken', () => {
    // Testing internal implementation
  });
});
```

---

## 🔍 Review Best Practices

### Review Mindset

1. **Be specific** - Point to exact lines, provide examples
2. **Be constructive** - Offer solutions, not just criticism
3. **Be thorough** - Check everything systematically
4. **Be fair** - Acknowledge good work too
5. **Be timely** - Don't let reviews pile up

### Security Review Checklist

Always verify:

- [ ] **Input validation** on all user inputs
- [ ] **Output encoding** for XSS prevention
- [ ] **Authentication** checks are in place
- [ ] **Authorization** is verified properly
- [ ] **Secrets** are not exposed
- [ ] **Logging** excludes sensitive data
- [ ] **Dependencies** don't have known vulnerabilities

### When to Request Re-review

- After addressing **any** blocking issue
- After significant changes (even if suggested)
- When unsure if the fix is correct
- Before merging critical features

---

## 🏗️ ADR Best Practices

### When to Create an ADR

Create an ADR when:
- Choosing between multiple valid approaches
- Making a decision that's hard to reverse
- Establishing a pattern for the codebase
- Adopting a new technology or library
- Changing an existing standard

### ADR Quality

A good ADR answers:
- **What** decision was made?
- **Why** was this option chosen?
- **What** alternatives were considered?
- **What** are the consequences?
- **How** do we implement it?

### Keeping ADRs Updated

- **Mark deprecated ADRs** - Don't delete, deprecate
- **Link superseding ADRs** - Maintain history
- **Review quarterly** - Are they still relevant?
- **Update after incidents** - Learn and document

---

## ⚡ Productivity Tips

### Keyboard Shortcuts (Suggested)

| Action | Shortcut |
|--------|----------|
| Init context | `/init` |
| Clear context | `/clear` |
| Check status | `/status` |
| Invoke agent | `@AGENT_NAME` |

### Session Workflow

```
# Morning Start
/init
/status

# For each task
@DEV [mode] Implement: [task]
@REV Review: [task]
/complete [task]
/clear

# End of day
/status  # See progress
# Commit and push
```

### Time Estimates

| Activity | Time |
|----------|------|
| PRD creation | 15-30 min |
| PRD review | 10-15 min |
| Task decomposition | 10-20 min |
| Per task (M size) | 30-60 min |
| Per review | 10-20 min |

---

## 🚫 Common Mistakes

### Mistake 1: Skipping `/init`

**Problem**: AI hallucinates about project structure
**Solution**: Always run `/init` at session start

### Mistake 2: Not using `/clear`

**Problem**: Context from previous task pollutes current work
**Solution**: `/clear` between every task

### Mistake 3: Vague user stories

**Problem**: PRD is incomplete or incorrect
**Solution**: Write detailed stories with acceptance criteria

### Mistake 4: Ignoring ADR violations

**Problem**: Inconsistent codebase
**Solution**: Either fix the code or update the ADR (with good reason)

### Mistake 5: Rubber-stamping reviews

**Problem**: Bugs and security issues slip through
**Solution**: Actually review the code, check the checklist

### Mistake 6: Giant tasks

**Problem**: Hard to implement, review, and track
**Solution**: Break down to 2-4 hour chunks maximum

---

## 📊 Metrics to Track

### Quality Metrics

| Metric | Target | How to Measure |
|--------|--------|----------------|
| Review pass rate (first time) | >80% | Reviews passed / Total reviews |
| ADR compliance | 100% | Violations found / Reviews |
| Test coverage | >80% | Coverage tool |
| Bug escape rate | <5% | Bugs found post-merge / Total bugs |

### Productivity Metrics

| Metric | Purpose |
|--------|---------|
| Tasks completed per day | Velocity tracking |
| Time from story to PRD | Planning efficiency |
| Time from PRD to first task complete | Startup time |
| Average task completion time | Estimation accuracy |

---

## 🎓 Learning Path

### Beginner
1. Master `/init`, `/clear`, `/status`
2. Complete one feature with core agents
3. Write your first ADR

### Intermediate
1. Create custom specialist agents
2. Optimize your workflow
3. Contribute ADRs proactively

### Advanced
1. Customize agent prompts for your domain
2. Create project-specific templates
3. Mentor others in the framework

---

**Remember**: The framework is a force multiplier. The more you invest in mastering it, the more it gives back.
