import { useState } from "react";
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";
import { Input } from "@/components/ui/input";

export default function BABON() {
  const [businessPlan, setBusinessPlan] = useState("");
  const [brandKit, setBrandKit] = useState("");
  const [marketingKit, setMarketingKit] = useState("");
  const [submitted, setSubmitted] = useState(false);

  const generateBABON = async () => {
    setSubmitted(true);

    await new Promise((resolve) => setTimeout(resolve, 3000));

    setBusinessPlan(
      "Business Idea: AI-Powered Resume Optimization\nTarget Market: Job Seekers, Career Coaches\nUnique Angle: Personalized AI resume feedback with instant job matching"
    );

    setBrandKit(
      "Brand Name: ResumeReactor\nLogo Idea: Futuristic 'R' with circuitry\nColors: Blue, Silver, Black\nDomain: resumereactor.ai"
    );

    setMarketingKit(
      "Landing Page Copy: Boost Your Resume with AI Precision\nCTA: Get Instant Feedback Now\nEmail Sequence: Welcome, Tips, Promo, Testimonial, Upsell\nSocial Post: \"Job hunting? Let AI supercharge your resume. Try ResumeReactor today!\""
    );
  };

  return (
    <div className="p-4 grid gap-4 max-w-xl mx-auto">
      <h1 className="text-2xl font-bold text-center">BABON - Be A Business Owner Now</h1>

      {!submitted && (
        <div className="mt-4">
          <div id="paypal-container-WU4R32EETBY98"></div>
          <script src="https://www.paypal.com/sdk/js?client-id=BAAG1AlZ_Q6xs2F5yto8CuUvbG83TAUia7XzprbySnTFEBXCyfDni9rCqOpbuRg2kb5KIRDT_d5N-ZJTnM&components=hosted-buttons&enable-funding=venmo&currency=USD"></script>
          <script>
            {`paypal.HostedButtons({ hostedButtonId: "WU4R32EETBY98" }).render("#paypal-container-WU4R32EETBY98")`}
          </script>
        </div>
      )}

      {submitted && (
        <>
          <Button onClick={generateBABON}>
            Launch BABON Kit
          </Button>

          {businessPlan && (
            <Card>
              <CardContent>
                <h2 className="text-xl font-semibold mb-2">Business Plan</h2>
                <pre>{businessPlan}</pre>
              </CardContent>
            </Card>
          )}

          {brandKit && (
            <Card>
              <CardContent>
                <h2 className="text-xl font-semibold mb-2">Brand Kit</h2>
                <pre>{brandKit}</pre>
              </CardContent>
            </Card>
          )}

          {marketingKit && (
            <Card>
              <CardContent>
                <h2 className="text-xl font-semibold mb-2">Marketing Kit</h2>
                <pre>{marketingKit}</pre>
              </CardContent>
            </Card>
          )}
        </>
      )}
    </div>
  );
}
