# AI Companion - Emotionally Intelligent Desktop Assistant

A next-generation, multilingual, emotionally intelligent desktop AI companion that combines custom intent-based processing with ChatGPT's intelligence. Features real-time emotion detection, voice input, and adaptive responses across English, Hindi, and Hinglish.

## Key Features

### Intelligence & Conversation
- **ChatGPT Integration**: Natural language understanding and generation
- **Intent Classification**: Offline intent detection for system commands
- **Multilingual Support**: English, Hindi, and Hinglish
- **Context-Aware**: Maintains conversation history and user preferences
- **Emotional Adaptation**: Adjusts tone based on detected emotions

### Emotion & Personality
- **Face Emotion Detection**: Real-time webcam-based emotion analysis
- **Text Emotion Analysis**: Detects sentiment from user messages
- **Dynamic Avatar**: Color-changing brain avatar reflecting current emotion
- **Empathetic Responses**: AI adjusts communication style based on user state
- **Emotion Trend Tracking**: Monitors emotional patterns over time

### Voice & Audio
- **Voice Input**: Google Speech Recognition with real-time transcription
- **Voice Output**: Text-to-speech responses
- **Hotword Detection**: Customizable activation keyword
- **Multi-language Speech**: Supports speech in multiple languages

### Memory & Learning
- **Long-term Memory**: SQLite database for persistent storage
- **Conversation History**: Full chat transcripts and context
- **User Preferences**: Learns and remembers user settings
- **Habit Tracking**: Records frequent topics and patterns
- **Memory Backup & Export**: Save and export memories to JSON
- **Self-Learning**: Improves responses through pattern recognition

### System Integration
- **Application Launching**: Open apps via voice command
- **File Operations**: Create, read, delete files safely
- **System Commands**: Execute system-level operations
- **Code Analysis**: Help with debugging and optimization
- **Workflow Automation**: Batch operations and scheduling

### User Interface
- **Modern Dark Theme**: Sleek PyQt6 interface
- **Real-time Transcript**: Live conversation display
- **Status Monitoring**: System state and AI status
- **Settings Panel**: Quick access to preferences
- **Memory Display**: View recent interactions
- **Beautiful Animations**: Smooth transitions and visual feedback

## System Architecture

```
User Input (Voice/Text)
    ↓
Audio Processor / Text Parser
    ↓
Intent Classifier
    ├─ System Command → Advanced Features
    ├─ Coding Help → Code Analyzer
    └─ General Chat → ChatGPT
    ↓
Emotion Detector
    ├─ Facial Analysis
    └─ Sentiment Analysis
    ↓
Response Generation (Emotionally Adapted)
    ↓
Memory Manager (Store Interaction)
    ↓
Output (Voice/Text/Visual)
```

## Technology Stack

**Frontend**
- PyQt6: Desktop GUI framework
- Qt Charts: Data visualization

**Backend**
- OpenAI GPT-3.5-turbo: Advanced language model
- SpeechRecognition: Voice input processing
- OpenCV & dlib: Face and emotion detection
- gTTS: Text-to-speech conversion

**Data**
- SQLite: Local memory and preferences
- JSON: Export format

**System Integration**
- subprocess: System command execution
- platform: Cross-platform compatibility

## Installation

### Quick Start (Windows)
```bash
install.bat
```

### Quick Start (macOS/Linux)
```bash
chmod +x install.sh
./install.sh
```

### Manual Installation
```bash
pip install -r requirements.txt
cp .env.example .env
```

### System Dependencies
- **Windows**: Download FFmpeg from https://ffmpeg.org/download.html
- **macOS**: `brew install ffmpeg`
- **Linux**: `sudo apt-get install ffmpeg libsm6 libxext6`

## Configuration

### Environment Variables (.env)
```
OPENAI_API_KEY=sk-...your-key...
SUPABASE_URL=https://...optional...
SUPABASE_ANON_KEY=eyJ...optional...
SUPABASE_SERVICE_ROLE_KEY=eyJ...optional...
```

### Settings
- **Language**: English, Hindi, or Hinglish
- **Hotword Sensitivity**: 1-100% (adjust for activation)
- **Emotion Mode**: Adaptive (automatic) or Manual
- **Memory**: Enabled/Disabled

## Usage

### Running the Application
```bash
python main.py
```

### Voice Commands Examples

**System Operations**
- "Open Chrome"
- "Open VS Code"
- "Create a file named notes.txt"
- "Delete this file"

**Information Queries**
- "What time is it?"
- "What's the weather?"
- "Tell me today's date"

**Creative & Coding**
- "Write me a poem"
- "Debug this Python code"
- "Generate a random story"
- "Help me learn JavaScript"

**General Chat**
- "How are you?"
- "Tell me something interesting"
- "What's the meaning of life?"
- "I need emotional support"

### GUI Components

**Left Panel: Avatar & Status**
- Brain avatar with emotion-based colors
- Current emotion display
- Language selector
- Sensitivity slider
- System status indicator

**Center Panel: Chat Interface**
- Conversation transcript
- Message input field
- Send, Listen, Clear buttons
- Real-time message display

**Right Panel: System Control**
- Memory & interaction history
- Quick settings display
- Save memory button
- Export conversation button

## File Structure

```
├── main.py                 # Application entry point
├── audio_processor.py      # Speech recognition & TTS
├── intent_classifier.py    # Intent detection engine
├── chatgpt_handler.py      # OpenAI API integration
├── emotion_detector.py     # Facial & text emotion analysis
├── memory_manager.py       # SQLite memory management
├── advanced_features.py    # System automation & helpers
├── lucide_icons.py         # UI icon generation
├── requirements.txt        # Python dependencies
├── .env.example           # Environment template
├── install.sh             # macOS/Linux installer
├── install.bat            # Windows installer
├── SETUP_GUIDE.md         # Detailed setup instructions
└── ai_companion_memory.db  # Local memory database
```

## Advanced Features

### Code Analysis
```python
from advanced_features import CodeAnalyzer

analyzer = CodeAnalyzer()
issues = analyzer.analyze_code(code_string, "python")
fix = analyzer.debug_error(error_message)
```

### System Automation
```python
from advanced_features import SystemAutomation

SystemAutomation.open_application("Chrome")
output = SystemAutomation.execute_command("ls -la")
info = SystemAutomation.get_system_info()
```

### File Operations
```python
from advanced_features import FileManager

FileManager.create_file("notes.txt", "Content here")
content = FileManager.read_file("file.txt")
files = FileManager.list_directory("/path")
```

### Smart Suggestions
```python
from advanced_features import SmartSuggestions

suggestion = SmartSuggestions.suggest_next_action(history, context)
optimized = SmartSuggestions.optimize_workflow(tasks)
prediction = SmartSuggestions.predict_user_need(interactions)
```

## Memory System

### Interaction Storage
Automatically saves:
- User input
- AI response
- Detected emotion
- Intent classification
- Timestamp

### Long-term Memory
Store important information:
- User preferences
- Personal details
- Habits and patterns
- Important notes

### Memory Operations
- View recent interactions
- Export to JSON
- Create backups
- Clear old data
- View statistics

## Customization

### Adding New Intents
Edit `intent_classifier.py` to add patterns:
```python
"new_intent": [
    r"pattern1\s+(.*)",
    r"pattern2\s+(.*)",
]
```

### Changing UI Theme
Modify colors in `main.py`:
```python
self.setStyleSheet("background-color: #custom-color;")
```

### Adding System Commands
Extend `advanced_features.py` with new functionality:
```python
@staticmethod
def new_command(param):
    # Your implementation
    pass
```

## Performance Optimization

- **Reduce Sensitivity**: Lower hotword sensitivity for faster activation
- **Clear Old Data**: Periodically clean up old interactions
- **Cache Models**: ChatGPT caches similar queries
- **Optimize Webcam**: Use lower resolution for faster emotion detection
- **Batch Operations**: Process multiple tasks efficiently

## Troubleshooting

### Issue: "Microphone not working"
```bash
python -c "import speech_recognition as sr; sr.Microphone().list_microphone_indexes()"
```

### Issue: "Camera not detected"
```bash
python -c "import cv2; cap = cv2.VideoCapture(0); print(cap.isOpened())"
```

### Issue: "OpenAI API error"
- Check API key validity
- Verify account has credits
- Check rate limits

### Issue: "Memory database corrupted"
- Delete `ai_companion_memory.db`
- App recreates it on restart

## Security & Privacy

- All local data stored in encrypted SQLite database
- API keys stored securely in `.env` (never committed)
- Optional cloud backup via Supabase
- No data collection without explicit consent
- Emotion data stored locally only

## Future Enhancements

- [ ] Vision-based task automation
- [ ] Email integration
- [ ] Calendar management
- [ ] Real-time news briefing
- [ ] Smart home integration
- [ ] Advanced productivity analytics
- [ ] Custom voice profiles
- [ ] Offline mode support

## API Reference

### AudioProcessor
```python
listen_and_transcribe()      # Listen and transcribe speech
play_response(text, lang)    # Text-to-speech output
detect_hotword(audio)        # Detect activation keyword
```

### IntentClassifier
```python
classify(input)              # Return (intent, confidence)
extract_entities(input)      # Extract named entities
get_context(input)          # Get full context analysis
```

### ChatGPTHandler
```python
get_response(msg, lang)     # Get emotionally-aware response
analyze_sentiment(text)     # Analyze text sentiment
generate_creative(prompt)   # Generate creative content
```

### EmotionDetector
```python
detect_emotion(image, text) # Detect emotion from sources
get_emotion_trend()         # Get emotional trend
suggest_response_tone()     # Get recommended tone
```

### MemoryManager
```python
save_interaction(user, ai)     # Save conversation
get_recent_interactions(n)     # Retrieve recent chats
save_preference(key, value)    # Store preferences
record_habit(name, context)    # Track habits
export_to_json(path)           # Export memories
```

## Contributing

Customization guide:
1. Modify core modules as needed
2. Add new features to `advanced_features.py`
3. Update intent patterns in `intent_classifier.py`
4. Test thoroughly before production use

## License

This application is built for personal use and customization.

## Support

For detailed setup help, see SETUP_GUIDE.md

---

**Built with ❤️ for intelligent, emotional computing**
