## Hi, I'm Mr T. 👋

```ts
// github-profile.ts
"use server";

/**
Very nerdy presentation, I know 😎
Let's just have fun, folks
*/
import { github } from "github/helpers"; // 🥲

type ProfileProps = {
  expertise: string[];
  passion: string[];
  teaching: string[];
  interest: string[]
}

const mrTProfile: ProfileProps = {
  expertise: ["JS/TS", "React/Next.js", "Drizzle ORM/Prisma ORM", "PostgreSQL/MongoDB"],
  passion: ["Developer Education", "AI Accessibility", "Career Growth"],
  teaching: ["Programming Fundamentals", "AI Integration"],
  interest: ["AI/ML", "Astronomy/Space Engineering"]
}

export async function displayProfile(mrTProfile){
  const { success, session } = await verifySession();
  if (!success || !session)
    return { message: "Please sign in to access this page" };

  try {
    const profileInfo = await github.loadProfileInfo(mrTProfile);
    return profileInfo;
  } catch(err: unknow) {
    const e = error as Error;
    console.error(`Something wrong happened: ${e.message}`);
  }
}
```

## Keep in touch
- <a href="https://cuttypiedev.vercel.app" target="_blank">My website</a>
- <a href="https://x.com/DorianTho5" target="_blank">X/Twitter</a>
