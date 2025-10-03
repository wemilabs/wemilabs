## Hi, I'm Mr T. 👋

```ts
// whoami.ts
"use server";

import { githubWebHelpers } from "github/web-helpers"; // 🥲 i couldn't resist

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

/**
* Very nerdy presentation, I know 😎
* Let's just have fun folks, while expressing a bit of creativity.
*/
export async function displayProfile(mrTProfile){
  const { success, session } = await githubWebHelpers.verifySession();
  if (!success || !session)
    return { message: "Please log in first to access this content." };

  try {
    const profileInfo = await githubWebHelpers.loadProfileInfo(mrTProfile);
    return profileInfo;
  } catch(err: unknow) {
    const e = err as Error;
    console.error(`Something wrong happened: ${e.message}`);
  }
}

// app/profile/page.tsx

// Coming soon...
```

## Keep in touch
- <a href="https://cuttypiedev.vercel.app" target="_blank">My website</a>
- <a href="https://x.com/DorianTho5" target="_blank">X/Twitter</a>
