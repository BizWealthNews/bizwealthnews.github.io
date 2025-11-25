# Combine checklist and 30-day timeline into a single structured sheet for Google Sheets

# Create checklist dataframe
checklist_items = [
    ["Branding & Visual Identity", "Logo finalized"],
    ["Branding & Visual Identity", "Color palette ready (Black, White, Slate Gray, Gold accents, Electric Blue for CTA)"],
    ["Branding & Visual Identity", "Fonts chosen (Montserrat, Bebas Neue, Anton, Gotham, Helvetica Neue)"],
    ["Branding & Visual Identity", "Carousel & post templates ready"],
    ["Content Assets", "30-day content calendar prepared"],
    ["Content Assets", "One-liner pack finalized"],
    ["Content Assets", "Carousel scripts ready"],
    ["Content Assets", "Reel ideas mapped"],
    ["Content Assets", "High-quality visuals sourced (athletes, entrepreneurs, cityscapes, silhouettes, lifestyle)"],
    ["Page Setup", "Instagram page created with selected handle"],
    ["Page Setup", "Bio written (minimal, elite, or mysterious style)"],
    ["Page Setup", "Highlight covers ready (optional)"],
    ["Page Setup", "Creator account set up (recommended)"],
    ["Engagement & Growth Strategy", "Posting frequency decided (2 Reels/day, 1–2 carousels/day, daily Stories)"],
    ["Engagement & Growth Strategy", "Algorithm strategy understood (original content, saves, shares, watch time, niche consistency)"],
    ["Engagement & Growth Strategy", "Hashtags decided (3–5 per post)"],
    ["Analytics & Tracking", "Google Sheets / Excel dashboard ready for tracking followers, reach, likes, saves, shares"],
    ["Analytics & Tracking", "Instagram Insights set up for real-time tracking (watch time, saves, shares, retention)"],
    ["Optional Early-Stage Boosts", "Engage with other mindset/high-performance accounts to get early visibility"],
    ["Optional Early-Stage Boosts", "Comment on related niche posts to attract targeted followers"],
    ["Optional Early-Stage Boosts", "Consider small, focused paid promotion to jumpstart reach (optional)"]
]

df_checklist = pd.DataFrame(checklist_items, columns=["Category", "Task"])
df_checklist["Type"] = "Checklist"
df_checklist["Day"] = ""  # No specific day

# Create timeline dataframe
timeline_items = [
    (1, "Page Setup", "Create IG page, add handle, set bio, logo, highlight covers, switch to Creator account"),
    (2, "Branding", "Upload first carousel template, set post fonts/colors, finalize style consistency"),
    (3, "Content Prep", "Prepare first 5 Reels, 3 carousels, 1–2 Stories per day"),
    (4, "First Post", "Publish first Reel + Carousel, monitor reach & engagement"),
    (5, "Engagement", "Reply to all comments, DM new followers, track shares & saves"),
    (6, "Content Prep", "Create next batch of Reels & carousel slides"),
    (7, "Analytics Setup", "Set up Google Sheets / Excel dashboard, track reach, likes, saves, shares"),
    (8, "Post Consistency", "2 Reels/day, 1 carousel/day, Stories 5–7/day; monitor performance"),
    (9, "Engagement Boost", "Comment on related high-performance pages, engage with niche audience"),
    (10, "First Review", "Check top-performing posts, retention, saves, shares, adjust content style"),
    (11, "Reels Optimization", "Add hooks, on-screen text, captions for better retention"),
    (12, "Carousel Optimization", "Test short vs long slides, save/share prompts"),
    (13, "Posting", "Continue daily 2 Reels + 1 carousel + Stories"),
    (14, "Engagement", "Respond to DMs, encourage shares, continue niche comments"),
    (15, "Mid-Month Review", "Track growth in followers, reach, saves, shares; adjust strategy if needed"),
    (16, "New Content Batch", "Prepare 5–7 Reels + 3 carousels for next week"),
    (17, "Reels Testing", "Try slightly different formats / pacing, monitor retention"),
    (18, "Carousel Testing", "Test text-heavy vs minimalist slides, monitor saves"),
    (19, "Posting", "Maintain schedule, track early engagement (first 30–60 mins)"),
    (20, "Engagement Push", "Encourage saves/shares in captions, continue DMs/comments"),
    (21, "Mini Series Launch", "Start a themed series (e.g., Discipline Monday / Mindset Wednesday)"),
    (22, "Content Prep", "Prepare next batch of Reels & carousels for consistent posting"),
    (23, "Reels Optimization", "Review watch time and retention for improvements"),
    (24, "Carousel Optimization", "Add call-to-action to encourage shares / saves"),
    (25, "Posting", "2 Reels + 1 carousel + Stories, continue engagement"),
    (26, "Growth Boost", "Collaborate with 1–2 niche accounts via comments or small shoutout"),
    (27, "Analytics Review", "Update dashboard, check growth trends, refine strategy"),
    (28, "Content Prep", "Prepare final week’s batch of content (Reels + Carousels + Stories)"),
    (29, "Posting", "Maintain schedule, focus on retention & saves"),
    (30, "Month-End Review", "Analyze 30-day performance, identify top-performing content & strategies for month 2")
]

df_timeline = pd.DataFrame(timeline_items, columns=["Day", "Category", "Task"])
df_timeline["Type"] = "Timeline"

# Combine both dataframes
df_combined = pd.concat([df_checklist, df_timeline], ignore_index=True)

# Reorder columns
df_combined = df_combined[["Type", "Day", "Category", "Task"]]

# Save as CSV for Google Sheets
combined_csv_path = "/mnt/data/The_JOAHP_Launch_Execution_Sheet.csv"
df_combined.to_csv(combined_csv_path, index=False)
combined_csv_path

