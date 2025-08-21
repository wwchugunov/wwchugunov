import { Card, CardContent } from "@/components/ui/card";
import { Progress } from "@/components/ui/progress";

export default function Skills() {
  const skills = [
    { category: "Frontend", items: [
      { name: "React / React Native", level: 70 },
      { name: "HTML / CSS", level: 95 },
      { name: "JavaScript", level: 80 },
    ]},
    { category: "Backend", items: [
      { name: "Node.js / Express", level: 80 },
      { name: "PostgreSQL / Sequelize", level: 60 },
    ]},
    { category: "Tools", items: [
      { name: "Git & GitHub", level: 90 },
      { name: "Docker", level: 40 },
      { name: "Automation (Excel/CSV, APIs)", level: 80 },
    ]},
  ];

  return (
    <div className="max-w-3xl mx-auto p-6 grid gap-6">
      {skills.map((block, i) => (
        <Card key={i} className="shadow-md border border-gray-200 rounded-2xl">
          <CardContent className="p-6 space-y-4">
            <h2 className="text-xl font-semibold text-gray-800">{block.category}</h2>
            <div className="space-y-4">
              {block.items.map((skill, j) => (
                <div key={j}>
                  <div className="flex justify-between mb-1">
                    <span className="text-gray-700">{skill.name}</span>
                    <span className="text-gray-500 text-sm">{skill.level}%</span>
                  </div>
                  <Progress value={skill.level} className="h-2 rounded-full" />
                </div>
              ))}
            </div>
          </CardContent>
        </Card>
      ))}
    </div>
  );
}
