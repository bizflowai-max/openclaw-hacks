# Agent-Browser: Token-Efficient AI Browser Automation

## What is agent-browser?

[agent-browser](https://github.com/vercel-labs/agent-browser) is a headless browser automation CLI for AI agents built by Vercel. It uses an **accessibility tree** instead of screenshots or full DOM, making it dramatically more token-efficient.

## The Token Efficiency Problem

| Method | Tokens |
|--------|--------|
| Full DOM / Screenshot | ~3,000-5,000 tokens |
| agent-browser | ~200-400 tokens |

**That's 10-15x fewer tokens!**

## How It Works

Instead of sending entire page screenshots or DOM to the AI, agent-browser provides:

- **Accessibility tree**: Only interactive elements with references
- **Element refs**: Like `@e1`, `@e2` - deterministic, exact targeting
- **Text output**: Readable content without the visual overhead

## Example

```bash
# Navigate and get interactive elements
agent-browser open bizflowai.net
agent-browser snapshot -i

# Output:
# - link "Our Work" [ref=e1]
# - link "Buy Now" [ref=e2]
# - link "Subscribe" [ref=e5]

# Click using reference
agent-browser click @e2
```

## Why We Use It

- **Cost savings**: 10-15x fewer tokens = cheaper API calls
- **Speed**: Less data = faster responses  
- **Reliability**: Element refs are deterministic, not guesswork
- **Accuracy**: 89.1% success rate on WebVoyager benchmark

## Credit

- **Vercel Labs**: For building agent-browser
- **Browser Use**: For pioneering AI browser automation
- **VelvaShark**: For the 3-layer memory concept

## Resources

- [agent-browser GitHub](https://github.com/vercel-labs/agent-browser)
- [Vercel Blog on Token Efficiency](https://dev.to)

---

*Part of the Mike & Max "King of Know-How" journey.*