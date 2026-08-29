# Family-Office-OS-x
Net worth dashboard for family offices managing $20M-$500M+ across multiple asset classes, currencies, and legal structures.

**Live demo:** https://family-office-os-two.vercel.app/

## What it does

Family offices upload bank statements and fund reports in PDF or Excel. The platform parses them automatically, extracts transaction data, and updates net worth across 10 asset classes in real time. No manual data entry. No file storage.

## Stack

Next.js 14, TypeScript, Tailwind CSS, NeonDB, Prisma, NextAuth, Recharts, Leaflet

## One hard decision

I chose to parse documents in memory and discard them immediately after extraction. Storing financial documents creates a massive liability surface area for auditors and increases GDPR risk. The trade-off is that parsing must be fast and accurate -- which is why I built confidence scoring to flag uncertain fields for human review instead of silently inserting bad data.
