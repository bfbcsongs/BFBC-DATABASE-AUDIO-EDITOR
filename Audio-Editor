'use client';
import { useState } from 'react';

export default function AudioEditor() {
  const [url, setUrl] = useState('');
  const [semitones, setSemitones] = useState(0);
  const [loading, setLoading] = useState(false);

  const handleProcess = async (e) => {
    e.preventDefault();
    setLoading(true);
    
    console.log("Processing URL:", url, "Shift:", semitones);
    
    setTimeout(() => {
      setLoading(false);
      alert("Audio Editor UI is working!");
    }, 1500);
  };

  return (
    <main className="max-w-xl mx-auto p-6 space-y-6 mt-10 bg-white shadow-md rounded-lg">
      <div className="border-b pb-4">
        <h1 className="text-2xl font-bold">🎵 Music Splitter & Transposer</h1>
        <p className="text-sm text-gray-500">Paste your YouTube link and adjust the key.</p>
      </div>

      <form onSubmit={handleProcess} className="space-y-4">
        <div>
          <label className="block text-sm font-medium mb-1">YouTube Link</label>
          <input 
            type="url" 
            value={url}
            onChange={(e) => setUrl(e.target.value)}
            placeholder="https://www.youtube.com/watch?v=..." 
            className="w-full p-2 border rounded-md"
            required
          />
        </div>

        <div>
          <label className="block text-sm font-medium mb-1">Transpose Key (Semitones: {semitones})</label>
          <input 
            type="range" 
            min="-12" 
            max="12" 
            value={semitones} 
            onChange={(e) => setSemitones(Number(e.target.value))}
            className="w-full cursor-pointer"
          />
          <div className="flex justify-between text-xs text-gray-400 mt-1">
            <span>-12 (Lower)</span>
            <span>0 (Original)</span>
            <span>+12 (Higher)</span>
          </div>
        </div>

        <button 
          type="submit" 
          disabled={loading}
          className="w-full bg-blue-600 text-white p-2 rounded-md font-medium hover:bg-blue-700 disabled:opacity-50 transition-colors"
        >
          {loading ? "Processing Audio..." : "Process Track"}
        </button>
      </form>
    </main>
  );
}
